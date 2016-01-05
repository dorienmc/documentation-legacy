---
## Device
Device events are emitted when a device (The Element, Raspberry Pi or another client) is connected or disconnected. These can be helpful when you want to listen to printers from a certain device.

---
### Connected
When a device is connected, the device.connected event will be emitted. You can listen to it like this:

```
socket.on('device.connected', function(err, deviceInfo) {
    // do something with deviceInfo
    // device info looks like this:
    
    /* {
        _id: "DEVICE_USER_CONNECTION_ID",
        client: "DEVICE_ID",
        clientToken: "DEVICE_API_TOKEN",
        name: "DEVICE_NAME",
        user: "USER_ID"
    } */
});
```
---
### Disconnected
When a device is disconnected, the device.disconnected event will be emitted. You can listen to it like this:

```
socket.on('device.disconnected', function(err, deviceInfo) {
    // do something with deviceInfo
    // device info looks like this:
    
    /* {
        _id: "DEVICE_USER_CONNECTION_ID",
        client: "DEVICE_ID",
        clientToken: "DEVICE_API_TOKEN",
        name: "DEVICE_NAME",
        user: "USER_ID"
    } */
});
```