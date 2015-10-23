---
## Log module
The core of the client has a logging module that is based on the node package `captains-log`.
Outputs look like this:

![](https://storage.googleapis.com/downloads.formide.com/cdn/images/formide-client-log.png)

### Levels
The logging module has several log levels that you can filter on based on the environment that the client
is running in (like development or production).

The levels are:
- error
- warn
- debug
- verbose
- silly
- info
