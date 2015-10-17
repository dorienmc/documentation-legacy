---
## Events
Emit and listen to system events or add your own event. All system events are automatically forwarded to any connected local or cloud websocket connection as well.

---
### Listening to events
You can listen to events that are triggered by the core system or by 3rd party modules.

```
FormideOS.events.on('slicer.finished', function(data) {
    console.log('slice data', data);
});
```

---
### Emitting events
You an also emit new events that other modules can listen to. This way, your modules can work together in real time. You can give your events any name you want, just be careful not to use any of the available system events. We suggest a naming scheme like MODULENAME.EVENTNAME to make use of the EventEmitter2's wildcard functionality.

```
something.on('data', function(data) {
    FormideOS.events.emit('myEventName', data)
});
```

---
### Available core events
We have made the following events available by default:

```
// slicer started slicing
FormideOS.events.on('slicer.started', function(data) {
    // data.printjob
});

// slicer finished slicing
FormideOS.events.on('slicer.finished', function(data) {
    // data.printjob
    // data.slicedata
});

// slicer failed
FormideOS.events.on('slicer.failed', function(data) {
    // data.message
    // data.code
});

// printer connected
FormideOS.events.on('printer.connected', function(data) {
    // data.port
});

// printer disconnected
FormideOS.events.on('printer.disconnected', function(data) {
    // data.port
});

// printer started printing
FormideOS.events.on('printer.started', function(data) {
    // data.port
    // data.printjob
});

// printer paused printing
FormideOS.events.on('printer.paused', function(data) {
    // data.port
    // data.printjobID
});

// printer resumed printing
FormideOS.events.on('printer.resumed', function(data) {
    // data.port
    // data.printjobID
});

// printer stopped printing
FormideOS.events.on('printer.stopped', function(data) {
    // data.port
    // data.printjobID
});

// printer finished printing
FormideOS.events.on('printer.finished', function(data) {
    // data.port
    // data.printjobID
});

// printer needs to be setup
FormideOS.events.on('printer.setup', function(data) {
    // data.port
});
```