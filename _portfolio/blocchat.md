---
layout: post
title: Bloc Chat
thumbnail-path: "img/Bloc-Chat-pixlr_microsoft-surfacebook-front"
short-description: Bloc Chat is chat room application.
---

{:.center}
![]({{ site.baseurl }}/img/Bloc-Chat-pixlr_microsoft-surfacebook-front.png)

## Background
Bloc Chat is a chat room application that utilizes a Firebase database and is my second project under the Bloc curriculum.

If web development is like swimming, then this project can be considered my first swim lesson without floaties. Supplemental code was limited for this project and the project instructions more or less reiterated the type of [structure and style guide](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) I'd be using for the project. Bloc did lay out the tasks and functionality to be developed and provided helpful resources. 

This project presented the opportunity to continue to work with Angular and solidify concepts such as controllers, services, and data-binding along with new concepts and functionalities such as databases, cookies, and modals.

## Features

Prompts for username and save as cookie.
![]({{ site.baseurl }}/img/blocchat/username.gif)

Creates new chat rooms.
![]({{ site.baseurl }}/img/blocchat/addroom.gif)

Contribute to chat rooms. 
![]({{ site.baseurl }}/img/blocchat/message.gif)

Tracks selected room, username, message, and time sent. 
![]({{ site.baseurl }}/img/blocchat/message.png)

## The Project: Build a Chat Application with Angular and Firebase

Bloc Chat is my first project working with a database which involved using new modules like (UI Bootstrap and ngCookies) and new functions that come with the territory. The key features of this application were to have the ability to list chat rooms, create new chat rooms, create and save a username to a cookie, and send and receive messages.

### Project Setup

1. Setup index.html file
  * Define frameworks and services being used
  * Link Bloc Chat application with Firebase database

![]({{ site.baseurl }}/img/Project Setup.png)
2. Set app.js file
  * Invoke Angular
  * Attach dependencies to the application
  * Add providers to define the application's home screen state

![]({{ site.baseurl }}/img/BlocChat_appjs.png)
3. Create a Home Controller
4. Create a Home html Template

### Challenge 1: How do I List Chat Rooms?

1. Create fake rooms through the Firebase site
2. Create a Room service to query the created rooms
  * Input the __`$firebaseArray`__ service as a dependency into the factory and pass it as an argument to the Room service 
  * Use Firebase's __```var ref = firebase.database().ref().child("rooms");```__ function in combination with the __```$firebaseArray(ref)```__ function in order to reference and query fake rooms
3. Create a Rooms template to display all rooms
  * Utilize the __```ng-repeat```__ directive and a data-binding to list all rooms 

### Challenge 2: How do I Create New Chat Rooms?

1. Create an add method within the Room service that will add room objects to the Rooms __```$firebaseArray```__
2. Create a button that opens a modal to create a new room using UI Bootstrap's __```$uibModal```__ service
  * Create an __```openModal```__ function to tie it to the Add Room button
  * Create a controller for the Modal and include a method to create a room and another to close the modal 
    * The __```$scope.createRoom```__ room method will utilize the add room method created in the Room service so the Rooms service will need to be injected as a dependency for the Modal controller
  * Tie the create room method to the Create Room button on the modal
  * Tie the cancel method to the Cancel button on the modal
  * Use the __```ng-model```__ directive on the Room Name textbox in order to pass the textbox value to the __```$scope.createRoom```__ method 

### Challenge 3: How do I List Messages for the Different Chat Rooms? 

1. Set up a method that captures a room's information when selected from the list and display the title in the message space 
  * Create two methods, one to set the selected room's value to null until a room is selected and the other to change the selected room's value from null to a specific room object 
  * Use the __```ng-click```__ directive on the listed rooms to set the selected room
  * Use the __```ng-show```__ directive to display the room title and contents when the selected room's value is no longer null
2. Create Message objects in Firebase with the following properties:
  * username:
  * content:
  * sentAt:
  * roomId: 
    * Use the roomId property to associate it with the room it pertains to
3. Query Message objects for a selected room using a message service
  * Use Firebase's __```var ref = firebase.database().ref().child("messages");```__ function in combination with the __```$firebaseArray(ref)```__ function in order to reference and query messages
  * Create a __```$scope.getByRoomId```__ method to return a room's roomId in the Message service
    * Use the __```getByRoomId```__ method within the __```$scope.selectRoom```__ method to pull the messages associated with the selected room 
  * Use __```ng-repeat```__ to list all messages in the content area
  * Use data-bindings to display the different properties 

### Challenge 4: How do I Set a Username?

1. Add the Angular cookies module to index.html and add __```ngCookies```__ module to the Bloc Chat app's dependency array
2. Set up a __```$cookies```__ service with a __```.run()```__ block to ensure a username is set when the application is initialized
3. Create a template and a controller for the username modal
  * The modal username template utilizes the __```ng-model```__ directive on the username textbox to pass the textbox value to the Username controller
  * Within the Username controller create a __```$scope.createUsername```__ method
    * The __```$scope.createUsername```__ method runs two important functions, one sets the username based on what is entered in the username textbox, the other function saves the username as a cookie on the application
  * Use a __```ng-submit```__ directive to invoke the __```$scope.createUsername```__ method when the username modal is submitted

### Challenge 5: How do I send Messages?

1. Create a __```$scope.send```__ method in the Message service
  * The __```$scope.send```__ method will add new messages to the messages __```$firebaseArray```__
2. Create a Message controller with a __```$scope.createMessage```__ method
  * The __```$scope.createMessage```__ method contains sub-methods to populates the new message's properties for __```roomId```__, __```content```__, __```username```__, and __```sentAt```__
    * Use a __```ng-model```__ directive on the message textbox to pass the textbox value to the __```$scope.content```__ sub-method
    * Use a __```new Date()```__ function to format the __```$scope.sentAt```__ sub-method
3. Use the __```ng-submit```__ directive on the Send button to invoke the __```$scope.createMessage```__ function
  * Ensure the function is being passed the selected room object so it's properties can be accessed and used by the __```$scope.createMessage```__ function

## What's Delivered

A functioning chat room application where new users can set their username and immediately start creating new chat rooms and contribute to existing chat rooms. 

## Lessons Learned

This project allowed me to get more experience integrating a 3rd party database application, and various new modules and services into my project. __```console.log()```__ was definitely a big help during the testing process of this project to verify how I was pulling and writing objects to the database, and making sure I was correctly accessing the object properties. This project felt like a big step in my progression and introduced me to new resources I can add to my tool belt. 








     












