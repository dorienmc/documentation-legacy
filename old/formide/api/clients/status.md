---
## Status
You can monitor the status of a user's devices using the API. You can for example create a desktop app or task bar menu to always keep an eye on the devices and printers that you're using.

---
### `GET` /clients
Get a list of all clients and their current session if online.

```
[
	{
		"_id": "55c8ff04d4beab38774ff593",
		"clientToken": "CLIENT_CONNECTION_TOKEN",
		"deviceType": "the_element",
		"isAdmin": false,
		"isOwner": false,
		"macAddress": "CLIENT_MAC",
		"name": "My Awesome Element",
		"permissions": [],
		"session": {
			"environment": "production",
			"geo": {
				"as": "YOUR ISP",
				"city": "Amsterdam",
				"country": "Netherlands",
				"countryCode": "NL",
				"isp": "YOUR ISP",
				"lat": 52.3666,
				"lon": 4.9027,
				"org": "YOUR ISP COMP",
				"query": "CLIENT_IP",
				"region": "NH",
				"regionName": "North Holland",
				"status": "success",
				"timezone": "Europe/Amsterdam",
				"zip": "1014"
			},
			"ip": "CLIENT_IP",
			"ip_internal": "CLIENT_INTERNAL_IP",
			"mac": "CLIENT_MAC",
			"port": 1337,
			"type": "client",
			"version": "0.2.0"
		},
		"status": "online",
		"tags": []
	}
]
```

---
### `GET` /clients/:clientId
Get a single client object by ID.

```
{
	"_id": "55c8ff04d4beab38774ff593",
	"clientToken": "CLIENT_CONNECTION_TOKEN",
	"deviceType": "the_element",
	"isAdmin": false,
	"isOwner": false,
	"macAddress": "CLIENT_MAC",
	"name": "My Awesome Element",
	"permissions": [],
	"session": {
		"environment": "production",
		"geo": {
			"as": "YOUR ISP",
			"city": "Amsterdam",
			"country": "Netherlands",
			"countryCode": "NL",
			"isp": "YOUR ISP",
			"lat": 52.3666,
			"lon": 4.9027,
			"org": "YOUR ISP COMP",
			"query": "CLIENT_IP",
			"region": "NH",
			"regionName": "North Holland",
			"status": "success",
			"timezone": "Europe/Amsterdam",
			"zip": "1014"
		},
		"ip": "CLIENT_IP",
		"ip_internal": "CLIENT_INTERNAL_IP",
		"mac": "CLIENT_MAC",
		"port": 1337,
		"type": "client",
		"version": "0.2.0"
	},
	"status": "online",
	"tags": []
}
```

---
### `GET` /clients/:clientId/sessions
Get the last 10 sessions of a client.

```
[
	{
		"__v": 0,
		"_id": "55d6b92174166da32f792cb7",
		"client": "55c8ff04d4beab38774ff593",
		"createdAt": "2015-08-21T05:37:37.590Z",
		"sessiondata": {
			"environment": "production",
			"geo": {
				"as": "YOUR ISP",
				"city": "Amsterdam",
				"country": "Netherlands",
				"countryCode": "NL",
				"isp": "YOUR ISP",
				"lat": 52.3666,
				"lon": 4.9027,
				"org": "YOUR ISP COMP",
				"query": "CLIENT_IP",
				"region": "NH",
				"regionName": "North Holland",
				"status": "success",
				"timezone": "Europe/Amsterdam",
				"zip": "1014"
			},
			"ip": "CLIENT_IP",
			"ip_internal": "CLIENT_INTERNAL_IP",
			"mac": "CLIENT_MAC",
			"port": 1337,
			"type": "client",
			"version": "0.2.0"
		},
		"updatedAt": "2015-08-21T05:37:37.590Z"
	}
]
```

---
### `POST` /clients/:clientId/sync
Start printer sync process for client

---
### `GET` /clients/:clientId/users
Get a list of all user client connections (only when admin user)

---
### `POST` /clients/:clientId/users
Invite a person to use a client

| **name** | **type** | **details** |
|:---|:---|:---|
| email | String | Email address of the person to invite |

---
### `PUT` /clients/:clientId/users/:userClientId
Update a user client connection

| **name** | **type** | **details** |
|:---|:---|:---|
| name | String | Name for the user client connection |

---
### `PUT` /clients/:clientId/users/:userClientId/admin
Update a user client connection's permissions (only when admin user)

| **name** | **type** | **details** |
|:---|:---|:---|
| isAdmin | Boolean | Set user client connection to admin or not |

---
### `DELETE` /clients/:clientId/users/:userClientId
Delete a user client connection (only when admin user)