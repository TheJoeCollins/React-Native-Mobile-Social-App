# React Native Social App

#### Introduction

This is a summary of my private repository for a type of Social App I have been working on in my free time. My goal is to release this on the app store after I complete the list of minimum features for the service. To still show off my React Native experience I created this repository to show some of the features that I have included with in the app to date.

#### About

All of the covered topics I have taught myself just through continous and unrelenting desire to become one of the best programmers to date. Any advice at all negative or positive is much desired.

#### Tech Stack

- React Native
  - Redux w/ Thunk
  - React Navigation
- Node.JS and Express.JS
- Ngnix as reverse proxy to the Express.JS Server managed by PM2
- Amazon EC2 Instance w/ Ubuntu
- Firebase Realtime Database
- MySQL

## App Examples

<img src="https://github.com/TheJoeCollins/React-Native-Mobile-Social-App/blob/master/assets/loginscreen.png" width="200px" height="400px" align="left" >
<img src="https://github.com/TheJoeCollins/React-Native-Mobile-Social-App/blob/master/assets/homescreen.png" width="200px" height="400px" align="left" >
<img src="https://github.com/TheJoeCollins/React-Native-Mobile-Social-App/blob/master/assets/communitys.png" width="200px" height="400px" align="left" >
<img src="https://github.com/TheJoeCollins/React-Native-Mobile-Social-App/blob/master/assets/communityevents.png" width="200px" height="400px"  >

- Login screen uses Firebase realtime database for authenticaion. 
- Facebook login works successfully and you can also sign up on the next page with just simple username and email. 
- I'm using **react-navigation** to handle my routes. When authorized it uses a switch stack to go from an unathorized stack to an authroized user stack of routes. 
- I also have an express server which upon successful firebase login takes the JWT and passes to also authenticate and retrieve additional user information from the MySQL database



## Inital Thought Process

What I managed to do is use Firebase for authentication. After being authenticated the returned JWT is then passed on an additional request to my Express.JS Server. Using the Firebase Admin SDK I verify the JWT and return additonal user information that is connected to my MySQL database. 

I originally built the application with Firebase NoSQL database but the information was clearly more relational and without substantial duplication on Firebase I decided it would be best to go with MySQL. I originally assumed this was the case but decided to personally test the **pros** and **cons** between the two big database types being currently used.

There may be a way to set this up for NoSQL that I did not see as the majority of my expertise is within MySQL and I am able to powerfully use inner joins and relational keys to enhance my feature set. Also all the data I have worked with so far is relational and the cascading deltes of MySQL has been very benefical.

## Current Features

- Create Communities
  - Users can create a community and others users can request membership
  - Admin functions to deny and accept user request, remove users
- Create Events
  - Events can be created and only shared within community members
  - Events are display on a map view using **React-Native-Maps**
  - Currently the map marker data is populated specifically by the user as I did google's maps API usages changed and charge $0.005 per request
- Search
  - Search based on three simple filters
  - Name completion search dynamically
  - Communities have a dynamic search for its community members
- Realtime Chat
  - Using firebase realtime database for user community chats
  - Built using **React-Native-Gifted-Chat**


## Structure

Another challenge has been deciding the most effective folder structure along with deciding the best place for resusable components. Eventually my structure became based of my navigation which I think is most ideal. The underlying folders however still need reorganizing. 

**Example:**

```
  --/src
       |--/appstack
            |-- /appstacknav (Tab Navigator and each tab gets its own Stack Navigator)
            |-- /HomeScreen
                  |--/Components
                  |--/HomeStackNav
            |-- /NextScreen
                  |--/...
       |--/assets
            |-- /...
       |--/authstack
            |-- /Login
       |--/backend
            |-- /API
            |-- /FirebaseConfig
       |--/config
            |-- /GlobalColorsEtc..
       |--/rootNavigator
            |-- /SwitchNavigator
       |--/reducers
          |--/reducer1
              |-- actions
              |-- reducer
              |-- constants
              |-- utils
          |--/reducer2
              |-- ...
``` 

This is a rough example of the strucutre but as you go lower into components I am still deciding on the best organizational structure.

## Future Features

- Push Notifications
  - I have used push notifcations in another simple demo with Amazons Pinpoint push notification service so I plan to implement a similar service but using soley firebase
- Social Sharing
  - Going to allow to share events information to various platforms and potentially allow for posting on behalf of the user
- Image Sharing
  - Currently looking at firebase storage to handle and store user images. Currently the only available viewed images is user profile images taken from facebook. 
  - Users who signup with email and password get a default image I created for the time being
  
## Security

I do not have a very exstensive background with security outside of JWT Tokens, data validation on both client and server. I am aware of libraries which will help such as Helmet.
One known issue that I do plan to fix that I know is the X-Powered-By header which just simply gives potential malicious users direct knowledge of the service backend used. Small issue but I am trying to be aware of more things I can do.


## Pitfalls

I have done basic testing in the past but not on this application which I am aware is a pitfall. My focus has mainly been 
focus on the MVP (Minimium Viable Product) and speed of developement. I do plan to go back and fix this problem which will probably cost me some time however as the sole developer I felt this wasn't the biggest problem as its really a punishment on myself at the moment.


## Timeline

This app to its current state was created within a month and a half. I set a goal near the beggining of June to complete the MVP by the end of august. The goal has been quite underestimated on purpose to test myself. 

Though the goal of this Mobile Application is release on the App store, I had an additional goal of becoming more adept with React Native and Javascript as a whole. This app also helps server as proof of my dedication to programming in general as I taught myself React and React Native to the current level of which I am now.

I hope in the future to complete the app in my free time and also gain industry level experience from senoir developers to guide me in becoming the best programmer that I can be.
  




