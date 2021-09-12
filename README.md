#  Share The Music <img src="https://github.com/pepes97/Share-The-Music/blob/master/portfolio-5.png" width="80" height="45">
Sveva Pepe, Francesco Scotti, and Claudia Medaglia created a project for Prof. Andrea Vitaletti's Reti di Calcolatori 2018/2019 course at the Sapienza University of Roma. 

# Requirements
1. The REST service you develop (we'll call it SERV) must have documented APIs (for example, GET /sanlorenzo returns all of Sanlorenzo's movies).
2. SERV must interact with at least two “external” REST services, i.e. not on localhost.
3. At least one of the external REST services must be commercial (es: twitter, google, facebook, pubnub, parse, firbase etc)
4. At least one external REST service must request oauth.
5. Websocket and/or AMQP must be used (o simili es MQTT)
6. The project must be hosted on GIT (GITHUB, GITLAB, etc.) and documented using a README file.

# Technologies Used 
* REST 1: Spotify (oAuth) 
* REST 2: songkick (API concerts) 
* REST 3: mapbox (API maps) 
* SocketIO: HTML5 (public and private conversation) 
* GitHub Documentation: MarkDown 

# Project Idea

Application that allows users to search for songs after they have logged in using Spotify.
The search result (if the song exists) will provide the user all relevant information about the song, including a Spotify link to the song and, if available, a 30-second preview.
By using the "Cerca Concerti" button, which sends a REST request to SongKick's API, you may get a list of concerts related to the artist of the song, complete with information on the city, date, and location of the event. 
By clicking on the location, a popup of a map with a marker indicating the event's location may be accessed through a MapBox REST API call.
It is always possible to use a private or public chat service on the concert page, created with the goal of being able to communicate with other users who have accessed the page to agree on the terms of a concert or, simply, to organise themselves to attend the performance together. 

# Descrizione Pagine

![Image](img/Mappa.PNG)

**Access**

The homepage displays the application's logo, followed by a brief explanation of what the site does with access to the main services. At the end of the introduction, there is a button that allows you to visit Spotify. After completing the login process, the user will be sent to the "Ricerca Canzone" page.

![Image](img/Login_page.png)

**Research**

The page has a simple search box where you can type in the name of the song or artist you're looking for. If these last two exist, the user will be redirected to the "Ricerca+Risultato" page; if they do not, the user will be redirected to the "404Traccia" page, which indicates that the search was unsuccessful.

![Image](img/Cerca1.png)

**Results**

The page will also have a search box, which can be used to start a new search, as well as all of the previous search results.
Each song will be identified by the album's cover art, the song's title, the artist's name, and the album's name.
Furthermore, if available, a 30-second preview of the song will be available.
Following that, there will be a link to Spotify, which will allow you to listen to the entire album on the platform. 
Finally, there is the "Cerca Concerti" button, which redirects you to the "Concerti" page if there are any scheduled concerts, or to the "404Concerti" page if your search yielded no results.

![Image](img/Risultati_traccia.png)

**Concerts**

The page will include a list of upcoming concerts as well as pertinent information about the city and state, as well as the date and location of the event. By clicking on the location, a popup of a map with a marker indicating the event's location will appear.
In the upper right corner of the page, there are two buttons labelled "Public Live Chat" and "Private Live Chat," which will redirect you to the pages "Chat Pubblica" and "Chat Privata," respectively (clicking on the "Public Live Chat" button will redirect you to the artist's ChatRoom).
![Image](img/Risultati_concerti.png)

**Public Chat**


The page is made up of a ChatBox and a text field where you can type your message (by using the "?" button, I got information on what commands I could use in the conversation).
On the left, there will be a list of ChatRooms, with the number of users online in each listed.
The user will first be sent to the artist's previously searched ChatRoom, but they may also choose to join an existing ChatRoom or create a new one (/join nomechat).
When a user enters or exits a ChatRoom, the list of rooms is automatically updated (elimination of ChatRooms, updating the number of users, alert("nomeutente è entratto nella room," etc.).
If there are no users in a conversation and you accept the default setting, the chat will be automatically cancelled.

![Image](img/pubblica.png)

**Private Chat**

The page includes a ChatBox, a text field for entering the nickname of the person with whom you like to communicate, an identification button for logged-in users, a text box for entering the message, and an email button.
It is necessary to be able to communicate with another user, but this latter has also gained access to a private chat room.

![Image](img/privata.png)

# Setup

1. Install Docker
[Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
2. Docker Compose
[Docker Compose](https://docs.docker.com/compose/install/)
****
In the docker-compose.yml change all its "volumes" with own oath, i.e., the path in 
which the directory is: 

`/ path  /ShareTheMusic:/home/node`


For example
```
/home/sveva/Desktop/University/ShareTheMusic:/home/node
```
# Run
```
docker-compose up
```




