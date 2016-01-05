---
### 1) Upload your app
Run the following command inside of the root folder of your app:

```
formide publish
```

Be sure to run this command in the root folder of your app.

---

### 2) Publishing your app
The second step is heading over to the app manager and go to the versions page of your app. There, you'll see a list of all you uploaded versions. When you're certain you want to publish a version, just click 'publish' behind the version number and your app will be online!

---

### Version management
We use semver to manage our app versions. This is standard practice throughout almost all package managers, so there's a big change you're already familiar with it. Our API will only accept an app version once, so when you make changed and upload again, the version number should be increased (this also automatically happens in your app.json file after uploading from the development kit).

Because of this behaviour, it is required to have an app.json file according to our specifications inside your project. A typical app.json file looks like this:

```
{
    "id":"123456789",
    "version":"0.0.1",
    "author":{
        "name":"Chris ter Beke",
        "email":"chris@printr.nl"
    }
}
```