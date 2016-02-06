---
Now your app is set up, users can authorise your application via our API so that they can use your app and you their data. The first step in letting user use your application is by redirecting them from your login page to our authorisation portal. If you use one of the libraries, the authorise function in that library will handle that. If you want to do it manually, use the following URL:

`https://api2.formide.com/auth/authorise?client_id=YOUR_CLIENT_ID&redirect_uri=YOUR_REDIRECT_URI&response_type=code`

The user will be redirected to our authentication portal were they will login or create an account. After that's done, the login portal will redirect back to you application's redirect URL (setup in the first step) with a authentication code in the query parameters (or an error if login failed).