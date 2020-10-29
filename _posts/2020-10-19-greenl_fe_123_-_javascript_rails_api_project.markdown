---
layout: post
title:      "GreenL!fe 123 - JavaScript Rails API Project"
date:       2020-10-19 13:06:36 -0400
permalink:  greenl_fe_123_-_javascript_rails_api_project
---

#### The Application was inspired by the 3 Pillars of Javascript, my love for plants & teaching my 4 year old son how to indentify a happy plant vs a sad plant.

#### A clean, fun, design showcasing some backend logic, AJAX requests, DOM manipulation & a`has_many` / `belongs_to` relationships between two Models. 

#### This blog post provides you with an outline of the different components pulled together to create this project. As simple as many apps may appear, there's a lot going on under the hood & many working part that come together to bring the App to life.



> ### Break it down to 3's

#### Most Web Apps consist of 3 main components:
>#### 1) `<HTML>`  This is where we construct our foundation for our we app. I like to look at it as the outline or skeleton `</HTML>`

>#### 2) .`CSS{ css is where we inject our styling. ie: color, font type, alignment, etc. }`

> #### 3 - `(JavaScript) => { console.log("javaScript is where we add our User interactivity")} `



### The 3 Pillars of Javascript

#### 1. *listen for events*
>#### `document.addEventListeners`("click", handleEvent) {console.log("event listeners are ears we stick in particular places that wait for something to happen for example a click on a button and is followed up with an event handler that will do something when that initial thing happens) }

#### 2. *handle events*
> ### Event handlers are the callback functions that directly respond the the event listener. for example if you add an event listener to the sumbit button of a form. We would add a callback function telling the submit click to do something, in this case "preventDefault" action from occuring so now our button knows hey when you are clicked no long do that, instead do this.


#### 3. *communicate with the server*
> ### `ApiService` Adapter methods are used to send information back to the server side to update the backend of changes, edits, updates, deletes that may have occured since last action.
> 


### Dual Directory

#### *The Project consists a dual directory named Frontend & Backend *




> ### *Rails API (Backend)*

#### Basic starter files include:

#### 1. Models
#### 2. Controllers
#### 3. Serializers


> ### *HTML, CSS, JavaScript (frontEnd)*

#### Basic starter files include:

#### 1. index.html
#### 2. index.js
#### 3. Class OOJS for model
#### 4. ApiService.js for Adapter Methods


### *Fetch(AJAX Request)*

#### Fetch is a relatively newer form of AJAX(Asyncronous Javascript and XML) request in which requests are made to the server without refreshing the browser allowing applications to run smoother by sending promises for information that may not be available at the moment but keeping the flow smooth. For example, syncronous experience is your UX consisting of having to wait a few seconds for some data to process before being able to move to the next step vs it happening on the backend and UX having no idea on data being processed on the backend as things on frontend appear to be running smoothly as expected correct?
