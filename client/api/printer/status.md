---
## Printer status

---
### GET /
Get a list and status of all attached printers.

```
{
    "ttyUSB1": {
        "status": 'printing'
        "bed": {
            "temp": 30,
            "targetTemp": 50
        }
        "extruders": [
            {
                "id": 'T',
                "temp": 200,
                "targetTemp": 203
            }
        ],
        "timeStarted": "Mon Jul 27 2015 20:23:21 GMT+0200 (CEST)"
        "timeNow": "Mon Jul 27 2015 21:07:45 GMT+0200 (CEST)"
        "totalLines": 340403,
        "currentLine": 203021,
        "progress": 59.64,
        "port": "/dev/ttyUSB1",
        "queueitemID": 32
    }
}
```

---
### GET /:port/commands
Get a list of commands available for a connected printer by port.

```
{
    "home": ["G28"],
    "home_x": ["G28 X"],
    "home_y": ["G28 Y"],
    "home_z": ["G28 Z"],
    "jog": ["G91", "G21", "G1 _axis_ _dist_"],
    "jog_abs": ["G90", "G21", "X_x_ Y_y_ Z_z_"],
    "extrude": ["G91", "G21", "G1 E _dist_"],
    "retract": ["G91", "G21", "G1 E _dist_"],
    "lcd_message": ["M117                     _msg_"],
    "temp_bed": ["M140 S_temp_"],
    "temp_extruder": ["M104 S_temp_"],
    "power_on": ["M80"],
    "power_off": ["M81"],
    "power_on_steppers": ["M17"],
    "power_off_steppers": ["M18"],
    "stop_all": ["M112"]
}
```

---
### GET /:port/status
Get the current status of a connected printer by port.

```
{
    "status": 'printing'
    "bed": {
        "temp": 30,
        "targetTemp": 50
    }
    "extruders": [
        {
            "id": 'T',
            "temp": 200,
            "targetTemp": 203
        }
    ],
    "timeStarted": "Mon Jul 27 2015 20:23:21 GMT+0200 (CEST)"
    "timeNow": "Mon Jul 27 2015 21:07:45 GMT+0200 (CEST)"
    "totalLines": 340403,
    "currentLine": 203021,
    "progress": 59.64,
    "port": "/dev/ttyUSB1",
    "queueitemID": 32
}
```