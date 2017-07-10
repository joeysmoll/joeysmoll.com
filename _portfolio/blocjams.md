---
layout: post
title: Bloc Jams
thumbnail-path: "img/landing_pixlr_microsoft-surfacebook-front.png"
short-description: BlocJams is a Spotify replica for playing music from an album.
---

{:.center}
![]({{ site.baseurl }}/img/landing_pixlr_microsoft-surfacebook-front.png)

## Background
Bloc Jams is a Spotify-like music application developed while doing my  apprenticeship under Bloc's software development program. Bloc presented the Bloc Jams project as a way to apply foundational front-end concepts. Bloc provided supplemental code throughout this project and challenged me to refactor the code multiple times to gain more experience working with the DOM and jQuery.   

## Features
Here are some of the defining features to enhance user experience.

MOBILE ready

{:.center}
![]({{ site.baseurl }}/img/mobile_album_pixlr_iphonesespacegrey_portrait.png)

HOLDS many albums

{:.center}
![]({{ site.baseurl }}/img/collection_pixlr_microsoft-surfacebook-front.png)

DISPLAYS album information

{:.center}
![]({{ site.baseurl }}/img/album_pixlr_microsoft-surfacebook-front.png)

PLAYS music

{:.center}
![]({{ site.baseurl }}/img/play_song.png)

TRACKS song progress and volume

{:.center}
![]({{ site.baseurl }}/img/player_bar.png) 


## The Real Project: Refactor Bloc Jams using Angular

The biggest challenge was learning about these new concepts - some of which are unique to Angular and others that apply to a broader selection of software - without compromising the existing user experience originally created using jQuery. 

### Challenge 1: Views and Routing

* Configure the angular module
* Bootstrap the application to the html using the __`ng-app`__ directive
* Create templates for the different webpages that will feed to the __`index.html`__
* Use __`ui.router`__ and __`<ui-view></ui-view>`__ to send different templates to `index.html`'s body 


### Challenge 2: Controllers

* Create XXXCtrl.js files for all views
* Instantiate controller when view is selected
* Access album data in template {{}} markup  


### Challenge 3: Album Service

* Create a service that pulls a selected album object
* Inject the service into the controller so album data can be accessed

### Challenge 4: Song Player Service

* Create a service that plays songs from the selected album  
* Inject the service into the controller so song data can be accessed
* Create a __`play`__ method to play a song
* Create __`pause`__ method to pause a song
* Utilize __`ng-show`__ and __`ng-click`__ directives to play/pause music and enhance UX 

### Challenge 5: Player Bar Service

* Create Player Bar controller
* Show Player Bar using __`<ng-include>`__ on the Album template
* Refactor play/pause methods so Album and Player Bar are in sync
* Create a __`next/previous`__ method to play next or previous song

### Challenge 6: Custom Directives - Seek Bar

* Create a Seek Bar directive - this directive creates two bars in the player bar to track/manipulate music progression and adjust volume level
* Make bar manipulation touch enabled for mobile use


### Challenge 7: Attributes and Directives

* Pass __`value`__ & __`max`__ attributes to the Seek Bar directive
* Create a method to observe when seek bar attributes change and track music progression in real time
* Create a __`volume`__ method to adjust volume level

### Challenge 8: Filters

* Create a __`timecode.js`__ filter for the song duration and progression so time is reformatted using minutes and seconds

## A Better Solution

Implementing Angular allowed Bloc Jams to run more efficiently when navigating between pages due to injecting html templates into the __`index.html`__ rather than replacing the page all together and reloading all parts like the navigation bar.     

## What's Delivered

{:.center}
![]({{ site.baseurl }}/img/play_song.png)

A successfully transformed Bloc Jams application that has identical functionality to my prior version built using jQuery.  

## Lesson Learned

Using multi-page or single-page solutions for applications will come with its compromises and I sacrificed a simple design structure for a more complex design in order to have a more efficient application.     

{:.center}
![]({{ site.baseurl }}/img/Compare.png)