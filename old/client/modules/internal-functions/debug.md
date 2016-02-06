---
## Debug
With debug you can log data in the console while running FORMIDEOS with your module manually. Debug logs are really useful for fixing errors or just to see what happens when your run FORMIDEOS. A debug line constist of a timestamp, the filename (automated) and a message that you sent.

![debug_line](./public/assets/images/formideos/debug_line.png)

---
### Functions

```
// log an information message
FormideOS.debug.log("This is a debug message for my module");

// log a possible error
FormideOS.debug.error("There is something bad going on!");
```

---
### Cloud
FORMIDEOS will automatically send debug messages to the cloud if the user enabled cloud debugging. It is not allowed to send any debug information to your own servers due to privacy reasons. We are working on a tool to let developers see debug information from all users that are running your module.