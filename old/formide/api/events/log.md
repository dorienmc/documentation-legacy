---
## Log
The logging events are emitted whenever something interesting happens. This can be an error, an important event (like a failed authentication) or just general debug information. Debug logs come in different priorities.

---
### Debug
Listen to debug information like authentication, started/stopped modules and binded slicer and driver binaries.

```
socket.on('log.debug', function(data) {
    // do something with data
    // the data object looks different depending on which module/function spawned the debug log but at least has a device id
    
    /* {
        device: "DEVICE_ID"
    } */
});
```