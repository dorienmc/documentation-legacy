---
The final part is obtaining an access token, which you need to call all protected api endpoints. You need to call the token authorisation endpoint with the code that you just got back from the login portal. See code examples below for the exact URL and parameters:

```
POST https://api2.formide.com/auth/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Host: api2.formide.com
Connection: close
Content-Length: 137
grant_type=authorization_code&client_id=YOUR_ID&client_secret=YOUR_SECRET&code=CODE
```

```
request.post({
    headers: {
        'content-type' : 'application/x-www-form-urlencoded'
    },
    url: this.formide.config.authUrl + '/token',
    strictSSL: false,
    form: {
        grant_type: 'authorization_code',
        code: tempCode,
        client_id: this.formide.config.apiKey,
        client_secret: this.formide.config.apiSecret,
        redirect_uri: this.formide.config.redirectURI
    },
    function( error, response, body ) {
        
    }
});
```

When your request is valid, you will get a response with an access token that you can use on the user's behalf to perform API requests:

```
{
    "access_token": "NEW_ACCESS_TOKEN",
    "refresh_token": "NEW_REFRESH_TOKEN",
    "expires": "EXPIRE_DATE"
}
```

Contratulations! You are now ready to do API calls like uploading files to a user's library, use the cloud slicer or work with data from users or public database.