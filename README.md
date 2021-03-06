# Introduction

> Qiscus Javascript SDK For Web

**Qis**cus SDK helps you build Web Chat Application easy and fast. It uses **qis**cus server backend for the API.
There's two version of the SDK. The SDK Core Only version which you can use to build a custom chat app without opinionated view layer.

# Quick Start
### 1. Create a new SDK application in the Dashboard and get app_id 
### 2. When integrating SDK with an existing app 
### 3. Running the 3.0 sample in React Native 

# Authentication 
### Initializing with APP_ID 
### Login or register
### Disconnecting/logout
### Updating a User Profile and Avatar 

# Room Types 
### Group Room 
### 1 on 1 

# 1-to-1 Chat 
### Creating and starting 1-to-1 chat

# Group Room 
### Creating a Group Room 
### Getting a Group Room instance with room id
### Inviting users to an existing room 
### Leaving a Group Room
### Advanced 
#### Getting a list of all room members
#### Getting participants' online statuses 
#### Typing indicators 
#### Read Receipts
#### Admin messages 
#### Room cover images 
#### Custom room types 
#### Custom message types 
#### Message auto-translation 
#### File Message thumbnails 

# Messaging
### Sending messages 
### Receiving messages
### Loading previous messages 
### Loading messages by timestamp
### Getting a list of participants in a room
### Getting participants' online statuses 
### Getting a list of banned or muted users in a room 
### Deleting messages 
    
# Room Metadata
### MetaData
### MetaCounter 

# Event Handler
### Room Handler 

# UI Customization
### Theme Customization 

# Miscellaneous 
# Change Log 

# Installation and Usage

## SDK with Integrated Widget View

This version let you add a chat widget directly into your existing HTML web pages. 
You just need to include the javascript and css files from the build directory. 
And you also need to append `<div id="qiscus-widget"></div>` tag before closing body tag. Here's sample HTML:

``` html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <link rel=stylesheet href=https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css>
  <link rel="stylesheet" type="text/css" href="https://s3-ap-southeast-1.amazonaws.com/qiscus-sdk/web/v1.5.0/css/qiscus-sdk.1.5.0.css">
  <!-- add this CDN for emojione if you intend to support emoji -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/emojione/2.2.7/lib/js/emojione.min.js"></script>
</head>
<body>
  <div id="qiscus-widget"></div>
  <script src="https://s3-ap-southeast-1.amazonaws.com/qiscus-sdk/web/v1.5.0/js/qiscus-sdk.1.5.0.js"></script>
  <script>
     qiscus.setUser('guest@qiscus.com', 'password', 'Qiscus Demo');
     qiscus.init({
        AppId: 'DRAGONGO',
        options: {
              loginSuccessCallback(data) { qiscus.UI.chatTarget('guest2@qiscus.com') },
              newMessagesCallback(data) { console.log("new message : ", data) }
        }
     });
  </script>
</body>
</html>
```

The javascript file introduce a new global variable called `qiscus`. We'll use that to initiate our chat widget.

``` javascript
// Set Current User for the Chat Widget
qiscus.setUser('email@email.com', 'key', 'username');
// Init the widget
qiscus.init({AppId: 'dragongo'});
// start chat with target
qiscus.UI.chatTarget('guest2@qiscus.com')
```

You can get `AppId` by requesting one from [sdk.qiscus.com](http://sdk.qiscus.com)

Example Demo App [qiscus-sdk-web.herokuapp.com](http://qiscus-sdk-web.herokuapp.com)


![qiscus SDK demo](sdk-show.png)

