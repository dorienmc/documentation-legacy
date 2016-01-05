---
## Printers

---
### `GET` /api/db/printers
Get a list of printers.

```
[
	{
		"_id":"55c9c44ed4beab38774ff5f5",
		"_keywords":[
			"felix",
			"robot"
		],
		"axis":{
			"x":1,
			"y":1,
			"z":1
		},
		"baudrate":115200,
		"bed":{
			"heated":true,
			"x":210,
			"y":200,
			"z":200
		},
		"client":"55475cb5be1f0d2c9b15c134",
		"createdAt":"2015-08-11T09:46:09.838Z",
		"downloads":0,
		"extruders":[
			{
				"id":0,
				"name":"New Extruder",
				"nozzleSize":400,
			}
		],
		"id":"55c8c5e14cfdbc78b7039d0a",
		"materials":[],
		"name":"Felix 3.0",
		"port":"/dev/tty.usbserial-A70392XK",
		"preset":false,
		"public":true,
		"sliceprofiles":[],
		"tags":[
			"felix",
			"3.0",
			"robotics"
		],
		"updatedAt":"2015-08-26T08:49:02.837Z"
	}
]
```

---
### `GET` /api/db/printers/:id
Get a single printer by ID.

```
{
	"_id":"55c9c44ed4beab38774ff5f5",
	"_keywords":[
		"felix",
		"robot"
	],
	"axis":{
		"x":1,
		"y":1,
		"z":1
	},
	"baudrate":115200,
	"bed":{
		"heated":true,
		"x":210,
		"y":200,
		"z":200
	},
	"client":"55475cb5be1f0d2c9b15c134",
	"createdAt":"2015-08-11T09:46:09.838Z",
	"downloads":0,
	"extruders":[
		{
			"id":0,
			"name":"New Extruder",
			"nozzleSize":400,
		}
	],
	"id":"55c8c5e14cfdbc78b7039d0a",
	"materials":[],
	"name":"Felix 3.0",
	"port":"/dev/tty.usbserial-A70392XK",
	"preset":false,
	"public":true,
	"sliceprofiles":[],
	"tags":[
		"felix",
		"3.0",
		"robotics"
	],
	"updatedAt":"2015-08-26T08:49:02.837Z"
}
```

---
### `POST` /api/db/printers
Add a new printer

| **name** | **type** | **details** |
|:---|:---|:---|
| name | String | Name of the printer |
| client | String | The ID of a client which the printer is connected to |
| port | String | The serial port name which the printer is connected to |
| baudrate | Int | The default baudrate of the printer. The driver also auto detects this. Baudrates usually are 115200 or 250000 |
| bed | Object | Object containing bed information |
| bed.heated | Boolean | Has the printer a heated bed or not |
| bed.x | Int | Size of the build envelope in the x direction |
| bed.y | Int | Size of the build envelope in the y direction |
| bed.z | Int | Size of the build envelope in the z direction |
| axis | Object | Object containing axis information |
| axis.x | Int | Direction of the x axis. 1 is normal, -1 is inverted |
| axis.y | Int | Direction of the y axis. 1 is normal, -1 is inverted |
| axis.z | Int | Direction of the z axis. 1 is normal, -1 is inverted |
| extruders | Object[] | Array of objects containing extruder information |
| extruders[n].id | Int | Position of the extruder in the firmware (usually an array index) |
| extruders[n].name | String | Name of the extruder for recognition (i.e. 'support material extruder' |
| extruders[n].nozzeSize | Int | Size of the nozzle in microns (usually 300 to 500) |
| tags | String[] | Array of tags for searching |

```
{
	"message": "printer added",
	"printer": { printer object }	
}
```

---
### `PUT` /api/db/printers/:id
Edit a printer

| **name** | **type** | **details** |
|:---|:---|:---|
| name | String | Name of the printer |
| client | String | The ID of a client which the printer is connected to |
| port | String | The serial port name which the printer is connected to |
| baudrate | Int | The default baudrate of the printer. The driver also auto detects this. Baudrates usually are 115200 or 250000 |
| bed | Object | Object containing bed information |
| bed.heated | Boolean | Has the printer a heated bed or not |
| bed.x | Int | Size of the build envelope in the x direction |
| bed.y | Int | Size of the build envelope in the y direction |
| bed.z | Int | Size of the build envelope in the z direction |
| axis | Object | Object containing axis information |
| axis.x | Int | Direction of the x axis. 1 is normal, -1 is inverted |
| axis.y | Int | Direction of the y axis. 1 is normal, -1 is inverted |
| axis.z | Int | Direction of the z axis. 1 is normal, -1 is inverted |
| extruders | Object[] | Array of objects containing extruder information |
| extruders[n].id | Int | Position of the extruder in the firmware (usually an array index) |
| extruders[n].name | String | Name of the extruder for recognition (i.e. 'support material extruder' |
| extruders[n].nozzeSize | Int | Size of the nozzle in microns (usually 300 to 500) |
| tags | String[] | Array of tags for searching |
| public | Boolean | Make printer publicly visible or not |

```
{
	"message": "printer updated",
	"printer": { printer object }	
}
```

---
### `DELETE` /api/db/printers/:id

```
{
	"message": "printer deleted"
}
```