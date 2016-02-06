---
## Materials

---
### `GET` /api/db/materials
Get a list of materials.

```
[
	{
		"_id":"55b7d766d2e8a1f89aed6753",
		"createdAt":"2015-07-28T19:26:30.251Z",
		"updatedAt":"2015-08-24T15:55:50.264Z",
		"firstLayersBedTemperature":60,
		"bedTemperature":50,
		"firstLayersTemperature":190,
		"temperature":190,
		"filamentDiameter":1750,
		"type":"PLA",
		"name":"PLA (1.75)",
		"user":"552d4a55db99a3c7449c891f",
		"_keywords":["pla","75"],
		"preset":false,
		"downloads":0,
		"public":true,
		"feedrate":100,
		"tags":["PLA"]
	}
]
```

---
### `GET` /api/db/materials/:id
Get a single material by ID.

```
{
	"_id":"55b7d766d2e8a1f89aed6753",
	"createdAt":"2015-07-28T19:26:30.251Z",
	"updatedAt":"2015-08-24T15:55:50.264Z",
	"firstLayersBedTemperature":60,
	"bedTemperature":50,
	"firstLayersTemperature":190,
	"temperature":190,
	"filamentDiameter":1750,
	"type":"PLA",
	"name":"PLA (1.75)",
	"user":"552d4a55db99a3c7449c891f",
	"_keywords":["pla","75"],
	"preset":false,
	"downloads":0,
	"public":true,
	"feedrate":100,
	"tags":["PLA"]
}
```

---
### `POST` /api/db/materials
Add a new material.

| **name** | **type** | **details** |
|:---|:---|:---|
| name | String | Name of the material |
| type | String | Type of the material (i.e. 'PLA', 'ABS' |
| filamentDiameter | Int | Diameter of the filament in microns (i.e. 1750 for 1.75mm filament) |
| feedrate | Int | Feedrate of the material in percentage (usually 100) |
| temperature | Int | Printing temperature of the material |
| firstLayersTemperature | Int | Printing temperature during the first layers |
| bedTemperature | Int | Temperature of the heated bed during printing |
| firstLayersBedTemperature | Int | Temperature of the heated bed for the first layers |
| tags | String[] | Array of tags for better searching |

```
{
	"message": "material added",
	"material": { material object }	
}
```

---
### `PUT` /api/db/materials/:id
Edit a material

| **name** | **type** | **details** |
|:---|:---|:---|
| name | String | Name of the material |
| type | String | Type of the material (i.e. 'PLA', 'ABS' |
| filamentDiameter | Int | Diameter of the filament in microns (i.e. 1750 for 1.75mm filament) |
| feedrate | Int | Feedrate of the material in percentage (usually 100) |
| temperature | Int | Printing temperature of the material |
| firstLayersTemperature | Int | Printing temperature during the first layers |
| bedTemperature | Int | Temperature of the heated bed during printing |
| firstLayersBedTemperature | Int | Temperature of the heated bed for the first layers |
| tags | String[] | Array of tags for better searching |
| public | Boolean | Make the material publicly visible or not |

```
{
	"message": "material updated",
	"material": { material object }	
}
```

---
### `DELETE` /api/db/materials/:id
Delete a material

```
{
	"message": "material deleted"
}
```