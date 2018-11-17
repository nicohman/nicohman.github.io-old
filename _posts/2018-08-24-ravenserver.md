---
layout: default
title: "ravenserver"
tags: js project
---

# ravenserver

[ravenserver](https://git.sr.ht/~nicohman/ravenserver) is a NodeJS-based online repository/package manager for [raven](https://git.sr.ht/~nicohman/raven) themes. It runs off of Express, with a MongoDB Database for storage. The MongoDB database has collections for users and themes, all of which are manipulated through a REST API, which both the web interface and raven make requests to. For the purposes of allowing for a third-party client or app to interact with a running ravenserver, I'll go over each endpoint.

### API

- POST /themes/report
	- This endpoint reports a theme for a specific reason. Required body fields:
		- name: The name of the theme you're reporting
		- reason: The reason the theme is being reported
		- info: Any additional information about the report

- POST /themes/meta/:name
	- This endpoint updates the metadata of a specific theme. Required query fields:
		- token: A valid login token
		- typem: The metadata you're updating(either screen or description)
		- value: The value to update to

- POST /themes/users/delete/:user
	- This endpoint permanently deletes a user's account and all owned themes. Required query fields:
		- token: A valid login token
		- pass: The user's password for verification

- POST /themes/delete/:name
	- This endpoint permanently deletes a theme. Required query fields:
		- token: A valid login token

- GET /themes/repo/:name
	- This endpoint returns a tarball of the named theme for downloading.

- POST /themes/upload
	- This endpoint creates or updates a theme. Required query fields:
		- name: Theme name
		- token: A valid login token
	- It also requires a multipart tarball of the theme to be uploaded. The maximum size is 50mb.

- POST /themes/user/create
	- This endpoint creates a new user. Required query fields:
		- name: The new user name. Must be unique
		- pass: The password to sign up with

- GET /themes/user/login
	- This endpoint takes a name and password and, if authenticated correctly, returns a login token. Required query fields:
		- name: Username
		- pass: Password to authenticate with

### Installation

To set up your own instance, it's pretty easy. First, grab the code:

*git clone https://github.com/nicohman/ravenserver*

Then, you'll need to set up a MongoDB database on the server. It should be named themes, and ravenserver will handle the rest of the setup. Now, you're pretty much ready to go. Just start it up!

*node app.js*

I personally recommend using [pm2](https://github.com/Unitech/pm2) to manage it.

*pm2 start app.js*
