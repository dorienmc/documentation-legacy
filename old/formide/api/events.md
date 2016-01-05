---
## Events

Just like with FORMIDEOS, you can listen to real time events with FORMIDE. The only difference is that you automatically listen to events from all connected clients for the logged in user.

You can connect to the websocket events with a socket.io client. Here's an example how to connect using socket.io for browser:

```
var socket = io("https://api2.formide.com");

// Emit authentication. You need an API access token and the type is 'user'
socket.emit('authenticate', {
    accessToken: "YOUR_ACCESS_TOKEN",
    type: "user"
}, function(err, success) {
    console.log(success);
});
```

As you can see, after connecting to the API with socket.io, you need to emit an authentication event to let our server know who the user is for this socket session. If the callback returns a successful response, the relevant events will come in.