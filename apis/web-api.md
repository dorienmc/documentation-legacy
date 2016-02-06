
---
## Web API
The FORMIDE web API allows you to integrate 3D printing into your websites and applications with just a few lines of code. Open up a world of possibilities to your users by using 3D printing technologies like slicing, remote printer control, settings and file management and real time notifications about all your connected 3D printers.

---
### Authentication
To authenticate on the Web API, you need to follow an OAuth2 flow (like Facebook and Twitter). Here is a step by step guide how to obtain the needed credentials and which API calls to make.

#### Register application
The first step is registering an application on the developers website (this site).

#### Obtain auth code
After registration and getting the client ID and secret, you can use these to start an authorisation flow for any platform user.

#### Obtain accesstoken
The final step is swapping the auth code for an accesstoken (and refreshtoken).

#### Do a call!
Now that you have the accesstoken, add it to any request as Bearer authorization header and make an API call.
