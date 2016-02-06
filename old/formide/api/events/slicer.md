---
## Slicer
The slicer module outputs events when you started slicing, when a slice is finished or when an error occurred. You can for example notify a user that slicing finished by using these events.

---
### Started
When the slicer started slicing, you get an event with data about the slice job.

```
socket.on('slicer.started', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        
    } */
});
```

---
### Finished
When the slicer finished slicing, you get an event with data about the finished slice job.

```
socket.on('slicer.finished', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        
    } */
});
```

---
### Failed
When an error occured during slicing, you'll receive an failed event with information about the error.

```
socket.on('slicer.failed', function(data) {
    // do something with data
    // data looks like this:
    
    /* {
        
    } */
});
```