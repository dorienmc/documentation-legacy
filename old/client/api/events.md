---
## Events
You can listen to real time events from the client through a websocket connection.

You can connect to the websocket events with a socket.io client. Here's an example how to connect using socket.io for browser:

```
var socket = io("http://YOUR_FORMIDE_CLIENT_IP:1337");

// Emit authentication. You need an API access token and the type is 'user'
socket.emit('authenticate', {
    accessToken: "YOUR_ACCESS_TOKEN",
    type: "user"
}, function(err, success) {
    console.log(success);
});
```

As you can see, after connecting to the API with socket.io, you need to emit an authentication event to let our server know who the user is for this socket session. This access token can be obtained via the `/auth/login` HTTP endpoint. If the callback returns a successful response, the relevant events will come in.