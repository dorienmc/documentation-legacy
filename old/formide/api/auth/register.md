---
### Register
The first step to connect your application to FORMIDE is actually registering it in the app center. Just click the block with a plus on it and fill in your app's name and select 'rest' under app type.

![register_app_1](./public/assets/images/formide/register_app_1.png)

After that, click on your app on the app center homepage and fill in the redirect URL under 'edit'. This URL is the url that we use to redirect to after a user authorised your application. Also make sure that you store your Client ID and Client secret somewhere safe, you will need them later to authorise to the api.

![register_app_2](./public/assets/images/formide/register_app_2.png)

---
### Preparing your app
The second step is preparing your application to connect to our api with the credentials that we gave you after registering your app (the Client ID and Client secret). The Client ID is a public key and will be visible when a user uses your application. The Client secret is a secret key that only should be filled in when you make a server to server connection with our api. For client to server connections, you can use another authorisation type that will be available soon.

The easiest way to setup your application is by using one of our client libraries. This way, you only have to enter your app credentials and call one of the api functions from the library. We currently have libraries available for Node.js and JavaScript. If you want to create an app for FORMIDE for 3D modelling, we strongly suggest you use our JavaScript 3D SDK.