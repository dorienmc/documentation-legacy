---
## Control printer

---
### GET /api/printer/:port/:command
Send a command (see commands endpoint to get a list of available commands) to one of your connected printers by port.

#### Example request
```
GET /api/printer/ttyUSB0/command/jog?axis=x&dist=10 HTTP/1.1
```

---
### GET /api/printer/:port/start
Get the current status of a connected printer by port.

#### Example request
```
GET /api/printer/ttyUSB0/start?hash=GCODE_FILE_HASH HTTP/1.1
```

---
### GET /api/printer/:port/stop
Stop a printjob running on the selected printer.

---
### GET /api/printer/:port/pause
Pause a printjob running on the selected printer.

---
### GET /api/printer/:port/resume
Resume a printjob running on the selected printer.
