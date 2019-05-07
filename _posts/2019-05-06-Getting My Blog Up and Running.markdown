---
layout: post
title:  "Getting the Blog Up and Running and a MEAN Stack demo"
date:   2019-05-06 18:37:00 -0500
categories: jekyll update
---

### MEAN Stack Heroku Deployed App

Here is a project that I worked on just demonstrating and familiarizing myself with different technologies that are out there.

### MEAN Stack

The MEAN stack is as follows:

    * MongoDB: The backend/database for the application
    * Express: The backend framework running on top of Node.js
    * Angular: The frontend framework that runs JavaScript code on the client end
    * Node.js: Used to implement your application backend in JavaScript

Find out more here! [MEAN Stack](http://mean.io)

The first project here is a Contact List application, where you can add a new, remove, and update your contacts. This follows the tutorial provided by Heroku, and is great for anyone looking to step into the world of the MEAN stack and wanting to learn how to deploy applications.

[Demo App](https://emr415plz.herokuapp.com)
[Tutorial](https://devcenter.heroku.com/articles/mean-apps-restful-api)

After doing that initial Contacts application, I went ahead and expanded on it. Made it to a Electronic Medical Records (EMR) application with a twist, I added Pessimistic Locking. Pessimistic Locking is where you lock the record while it is being used by someone. That way you avoid merge conflicts if someone else attempts to edit the record. To see the application with Pessimistic Locking, check out the link below:

[Pessimistic Locking App](https://enigmatic-tor-80276.herokuapp.com)

Look for a future post where I go into detail of Pessimistic Locking and how it is implemented in this app!