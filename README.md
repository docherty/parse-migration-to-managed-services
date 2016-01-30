# Migrating/replacing Parse.com with 3rd party managed services

## Background/Objectives
In light of the news that Parse.com is shutting down, we need to find an alternative. The Parse team have been great to support the community (they've Open Sourced the Parse server code etc). So there is a lot of discussion and effort being placed on using the Open Source code to set up a privately managed instance of Parse. This is fine if you have the time/smarts to do that professionally (or just want to play with it) but I don't. I want to move to a scenario where _all the management of the infrastructure and services is taken care of by someone else and all I have to worry about is my app's code and any custom backend logic I need_.
### Our use case
For info, my use case is pretty simple. We've developed a small Cordova (Ionic) app which uses Facebook oAuth and Parse user login. We use the Parse.User object to mirror data from within the app to the backend. Cloud code is used for a custom API (basically spits out JSON which is consumed by the app). Parse hosting is used for a simple marketing website and some static assets which is hit from within the app.

## Options to consider
### Core data
- MongoLab
- Firebase

### Cloud code
I'm looking for a decent managed node.js provider. I had heard of nodejitsu and since their acquisition, it looks like they're pointing users to Modulus.io . I don't want to run my own node server if I can avoid it.
- modulus.io
- Heroku (not sure how 'managed' this is)
- Amazon EB (ditto)
- Google Cloud (ditto)

### Push notifications
I haven't been using this in production but we know we're going to build it in in a release coming in the next couple of months so I need a solution. I've previously looked at all the usual suspects like UrbanAirship etc. Will probably depend on the Core data solution I choose and how users are managed.
- UrbanAirship etc.
- Amazon SNS
- Google Cloud

### Analytics
I have been using keen.io for analytics (we need some custom stuff) and didn't use Parse's offering. I'll probably move to Flurry for 'vanilla' analytics.
- Flurry
- Google Analytics
