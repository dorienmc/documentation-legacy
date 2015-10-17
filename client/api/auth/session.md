---
## Session

---
### POST /login
#### Example request
```
{
	"username": "admin@local",
	"password": "admin
}
```

#### Response
```
{
	"success": true,
	"session": {
    	"access_token": "YOUR_ACCESS_TOKEN"
    }
}
```

---
### GET /session
#### Response
```
{
	"success": true,
	"session": {
    	"access_token": "YOUR_ACCESS_TOKEN"
    }
}
```
