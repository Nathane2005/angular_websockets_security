angular_websockets_security
===========================

[![Build Status](https://travis-ci.org/Rob-Leggett/angular_websockets_security.svg?branch=master)](https://travis-ci.org/Rob-Leggett/angular_websockets_security)

Angular JS with Bootstrap, Web Sockets, Spring 4, and Spring Security

This example is an angular js single page application (SPA) with bootstrap for the widgets and styling.

The application has been broken into four modules RESTFUL-API, WEBSOCKET-API, SECURITY and CLIENT, all are built separately and all are deployed separately.

The RESTFUL-API and WEBSOCKET-API can run on any web server, but it has been tested against Tomcat 8, the server required http DELETE and PUT, so ensure your web server can support those http methods.

The CLIENT currently is run via gulp, for a production release you could extract the .zip artefact and run the static client via Apache.

Ensure that you proxy the RESTFUL-API and WEBSOCKET-API so that you have the same domain otherwise you will experience CORS related issues. (deployed artefacts only)

### Gulp:
Used as the build tool for the client, this has been written using ES6

### Spring 4:
Used to create RESTful controller interfaces which in turn gets called through ajax requests.

### Spring Security 4:
Used for a stateless api that allows authentication via basic authentication or token authentication.

Upon authentication a token is attached to the header response which can in turn be used for sequential requests to be authenticated against.

When an authentication fails a 401 will always be returned.

### Login Details as per database inject.sql:
**Username =** user@example.com

**Password =** password

Testing
====================
Simply run on the parent pom to have node and modules auto install and execute all tests. **(REQUIRED FOR FIRST RUN)**

Ensure you have Maven 3.2.0+

**mvn clean install**

To run specific profiles please run mvn clean install and simple pass the profile you wish to execute.

This will execute Java and Jasmine tests that will test both java classes and angular js files.

You can also run jasmine only tests if you wish via the front end:

**http://localhost:4444/test**

Running
====================

### Recommendations:

Use IntelliJ 16+ to run the application.

### Run the API via Tomcat 8:

Deploy exploded artefact to Tomcat 8 and ensure the root context is set to API.

### Run the restful api

The default is expecting the context root to be /restful and running on port 8084

### Run the websocket api

The default is expecting the context root to be /websocket and running on port 8085

### Run the CLIENT via gulp.babel.js:

Where PATH is the directory to your checked out project.

**Gulp File:** PATH\angular_websockets_security\client\gulpfile.babel.js

**Tasks:** run

**Node Interpreter:** PATH\angular_websockets_security\client\node\node.exe

**Gulp package:** PATH\angular_websockets_security\client\node_modules\gulp

### The application is set to run on

**http://localhost:4444**