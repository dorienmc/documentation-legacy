---
## Errors
The API can give 2 types of responses to every request: a success and and error response. The success response depends on the endpoint and can be very different for each one (check the API docs for all success responses). The error responses are generic and follow the following format:

```
{
	"statusCode": ERROR_CODE,
	"message": "ERROR_MSG",
	"error": "ERROR_DESCRIPTION"
}
```

---
### Not found example (404)

```
{
	"statusCode": 404,
	"message": "A printer with ID 2303 could not be found",
	"error": "Resource not found"
}
```

---
### Bad request example (400)

```
{
	"statusCode": 400,
	"message": "The following parameter was missing: bedTemperatre",
	"error": "Missing parameter"
}
```