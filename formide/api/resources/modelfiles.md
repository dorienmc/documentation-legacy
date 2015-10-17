---
## Modelfiles

---
### `GET` /api/db/modelfiles
Get a list of modelfiles.

```
[
	{
		"_id": "55c86237508c2c3f31cad6dc",
		"_keywords": [
			"iphon",
			"pattern",
			"case",
			"stl"
		],
		"analysis": {
			"finished": false
		},
		"app": {
			"_id": "5535a54f123a8a3f30260fda",
			"createdAt": "2015-05-25T15:39:41.179Z",
			"deleted": false,
			"name": "myaccount.formide.com",
			"oauthClient": "5535a54f123a8a3f30260fd9",
			"tags": "derp2",
			"type": "rest",
			"updatedAt": "2015-06-02T17:23:54.013Z",
			"user": "552d4a55db99a3c7449c891f"
		},
		"createdAt": "2015-08-10T08:35:03.373Z",
		"downloads": 0,
		"filename": "Iphone 5 pattern case",
		"filesize": 0,
		"filetype": "stl",
		"hash": "04a558af-6118-4df9-9fec-207837a5a7a9",
		"images": [
			{
				"_id": "55db77395366321d0b7eae48",
				"createdAt": "2015-08-24T19:57:45.245Z",
				"filename": "screenshot 1",
				"filesize": 85335,
				"filetype": "png",
				"hash": "cef371e8-4509-4480-9526-635498c23992",
				"type": "modelfile",
				"updatedAt": "2015-08-24T19:57:45.245Z",
				"user": "552d4a55db99a3c7449c891f"
			}
		],
		"prettyname": "Iphone 5 pattern case",
		"public": true,
		"tags": [],
		"updatedAt": "2015-08-24T15:42:15.393Z",
		"user": "552d4a55db99a3c7449c891f"
	}
]
```

---
### `GET` /api/db/modelfiles/:id
Get a single modelfiles by ID.

```
{
	"_id": "55c86237508c2c3f31cad6dc",
	"_keywords": [
		"iphon",
		"pattern",
		"case",
		"stl"
	],
	"analysis": {
		"finished": false
	},
	"app": {
		"_id": "5535a54f123a8a3f30260fda",
		"createdAt": "2015-05-25T15:39:41.179Z",
		"deleted": false,
		"name": "myaccount.formide.com",
		"oauthClient": "5535a54f123a8a3f30260fd9",
		"tags": "derp2",
		"type": "rest",
		"updatedAt": "2015-06-02T17:23:54.013Z",
		"user": "552d4a55db99a3c7449c891f"
	},
	"createdAt": "2015-08-10T08:35:03.373Z",
	"downloads": 0,
	"filename": "Iphone 5 pattern case",
	"filesize": 0,
	"filetype": "stl",
	"hash": "04a558af-6118-4df9-9fec-207837a5a7a9",
	"images": [
		{
			"_id": "55db77395366321d0b7eae48",
			"createdAt": "2015-08-24T19:57:45.245Z",
			"filename": "screenshot 1",
			"filesize": 85335,
			"filetype": "png",
			"hash": "cef371e8-4509-4480-9526-635498c23992",
			"type": "modelfile",
			"updatedAt": "2015-08-24T19:57:45.245Z",
			"user": "552d4a55db99a3c7449c891f"
		}
	],
	"prettyname": "Iphone 5 pattern case",
	"public": true,
	"tags": [],
	"updatedAt": "2015-08-24T15:42:15.393Z",
	"user": "552d4a55db99a3c7449c891f"
}
```

---
### `DELETE` /api/db/modelfiles/:id
Delete a modelfile.

```
{
	"message": "modelfile deleted"
}
```

> Note that deleting a file not actually deletes this file from our server but only removes the database entry for it.