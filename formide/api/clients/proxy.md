---
## Proxy
FORMIDE includes a full HTTP proxy for FORMIDEOS. you can call all REST endpoints you can on FORMIDEOS locally via the cloud as well. The only difference is the root URL of the API. Down here's an example that shows the difference in getting the active printer list:

```
GET /api/printer HTTP/1.1
Host: http://localhost:1337
Authorization: Bearer {{accessToken}}
```

```
GET /clients/:clientId/api/printer HTTP/1.1
Host: https://api2.formide.com
Authorization: Bearer {{accessToken}}
```

For a full list of available FORMIDEOS (proxy) endpoints, go to the [client HTTP docs](/#/docs/client/api).

---
### `ANY` /clients/:clientId/:yourProxyRequest
Do a proxy request to a specific client. Supports all HTTP methods.