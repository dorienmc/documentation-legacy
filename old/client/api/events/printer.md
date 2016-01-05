---
## Printer
You can listen to real time events from any connected printer. This includes connecting/disconnecting printers, status updates, print progress and notifications from your active prints.

---
### Connected

```
socket.on('printer.connected', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME"
    } */
});
```

---
### Disconnected

```
socket.on('printer.disconnected', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME"
    } */
});
```

---
### Status

```
socket.on('printer.status', function(status) {
    // do something with status
    // status looks like this:
    
    /* {
        device: "DEVICE_ID",
    } */
});
```

---
### Started

```
socket.on('printer.started', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME",
        printjobID: ID_OF_CURRENT_PRINTJOB
    } */
});
```

---
### Paused

```
socket.on('printer.paused', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME",
        printjobID: ID_OF_CURRENT_PRINTJOB
    } */
});
```

---
### Resumed

```
socket.on('printer.resumed', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME",
        printjobID: ID_OF_CURRENT_PRINTJOB
    } */
});
```

---
### Stopped

```
socket.on('printer.stopped', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME",
        printjobID: ID_OF_CURRENT_PRINTJOB
    } */
});
```

---
### Finished

```
socket.on('printer.finished', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        device: "DEVICE_ID",
        port: "SERIAL_PORT_NAME",
        printjobID: ID_OF_CURRENT_PRINTJOB,
        stats: {
            totalTime: "TOTAL_PRINTING_TIME_IN_SECONDS"	
        }
    } */
});
```

---
### Setup
To setup a new printer, you can listen to `printer.connected` and check if the port that's in the data object is already configured or not. This is already taken care of by the default interface that ships with the client.
