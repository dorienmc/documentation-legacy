---
## Tokens
Tokens (or access tokens) are used to authorise a user on an endpoint. When a user logs in, you get an access token back. In the cloud, we use oauth2 to do this, on the client a simpler direct exchange is safe enough because we don't have 3rd parties accessing user data using these tokens.

---
### GET /tokens
Get all tokens that have been issued. Tokens can original from a local login attempt or via the cloud. On a cloud login, the cloud register token is used by the FORMIDE platform to exchange for an access token for the user that is requesting access (taking into account their permissions).

Example response
```
[
    {
        "createdAt": "2015-08-13T14:26:32.133Z",
        "updatedAt": "2015-08-13T14:26:32.133Z",
        "token": "9fbc811a-e7f5-4205-a536-a62be48f6f95",
        "user": "2",
        "sessionOrigin": "local",
        "_id": 2,
        "__v": 0,
        "permissions": [
            "admin"
        ]
    },
    {
        "createdAt": "2015-08-13T14:31:18.758Z",
        "updatedAt": "2015-08-13T14:31:18.758Z",
        "token": "e7040e0f-8820-4bbd-8cda-cdecc57581c9",
        "user": "552d4a55db99a3c7449c891f",
        "sessionOrigin": "cloud",
        "_id": 3,
        "__v": 0,
        "permissions": []
    }
]
```

---
### POST /tokens
Manually create a new token with certain permissions.

Example request
```

```

Response
```

```

---
### DELETE /tokens/:id
Delete a token (e.g. revoke access using that token).
