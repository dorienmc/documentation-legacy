---
## User

---
### `GET` /auth/me
With this endpoint, you can get general information from the user like username, name and avatar.

#### Request
```
GET /auth/me HTTP/1.1
Host: https://api.formide.com
Authorization: Bearer {{accessToken}}
Cache-Control: no-cache
```

#### Response
```
{
  "_id": "552d4a55db99a3c7449c891f",
  "avatar": "https://storage.googleapis.com/formide-images/0fb5b81e-5bd0-42d5-b50b-f2e886f8429d",
  "firstname": "Chris",
  "lastname": "ter Beke"
}
```

---
### `POST` /auth/me