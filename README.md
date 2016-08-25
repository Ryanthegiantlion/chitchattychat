# chitchattychat

A chat prototype composed of four projects:

* [The apps for IOS and Android written in react native](../../../chitchattychat-app)
* [The web client](../../../chitchattychat-web-client)
* [The realtime server](../../../chitchattychat-realtime)
* [The api](../../../chitchattychat-api)
* TODO: The chatbot - add to github

# Live setup on Heroku:

## Prerequisites

* Make sure you have the heroku toolbelt installed
* Install [webpack](https://webpack.github.io/)
* Install react-native

Clone all the above repos into a root chat folder and navigate to that chat folder.

1. Live API

  ```
  cd chat-api
  heroku create --region eu
  heroku addons:create heroku-redis:hobby-dev
  heroku addons:create mongolab:sandbox
  git push heroku master 
  ```

2. Socket server
  ```
  cd ..
  cd socket-chat-server
  heroku create --region eu
  heroku addons:attach heroku-redis
  heroku features:enable http-session-affinity
  git push heroku master
  ```
  
3. Chat bot
  TODO: Add instructions some time

4. Web client
  edit: add how to buid with webpack and add that only copy index.html, css and js files
  Change apiurl and socketurl in index.html to those corresponding to heroku apps
  deployed to a static hosting provider such as s3: http://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html

5. React native
  TODO: This is out of date
  Change urls (currently in actions.js and /chat/index.js but need to be put in a better spot)

## Local setup

I will flesh this out in time but for now a good start would be to install redis and mongodb and get the demons running (this will get you hald the way there)
