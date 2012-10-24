# The state of Realtime at &yet

---

Henrik Joreteg

## What is a web app?

+	web, desktop, cli, mobile

## API is very core

+	Restful API
	+	doesn't always describe it the best way
+	Web API is functionality
	+	addUserToGroup(user, group);
+	Simple Unified Authentication (settle for oAuth)
+	The "official" app is just another client to the API

## Full Data Eventing

## Transports to API

+	websockets
+	ServerSentEvents
+	socket.io
+	rest
+	etc.

## Build Spec first

+	build everything else off the spec
+	defining a bunch of available functions
+	can create automatic documentaiton - smoke tests

## Redis as an App Server

+	any time data changes, emit events that contain enough data to describe event
+	they put their user actions in Redis as lua scripts
	+	events are automatically encapsulated within user actions (in Redis)
	+	Redis is a sort of application server
+	clients don't have to be aware of how to emit the events

...Basically, realtime is easy if you are building a NEW application from top to bottom