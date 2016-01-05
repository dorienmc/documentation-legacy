---
## Session

---
### POST /api/auth/login
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
### GET /api/auth/session
#### Response
```
{
	"success": true,
	"session": {
    	"access_token": "YOUR_ACCESS_TOKEN"
    }
}
```
