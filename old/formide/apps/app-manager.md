---
### App Manager
To make managing your apps and version even easier, we've developed an online [app manager](/#/apps). In this manager, you can see an overview of all your apps (including FORMIDE apps and Rest API apps), uploaded versions and permissions. You can also run all app versions in your browser and decide which version should be published to the FORMIDE App store.

> Note that when you delete an app version or app from the app manager, we will still hold on to it's original files.

---

### Storage
We store all apps and version in Google Cloud Storage. These files are publicly available. Don't put any secrets or password in the source of your app. Because of the App Store setup, you don't have to add any user credentials to an app, this is all taken care of when you use the 3D SDK.