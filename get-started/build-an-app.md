
---
## Build your first app
With the FORMIDE app platform, you can get your 3D content to end users and give them the ability to customize and adapt models before sending it directly to their 3D printer.

### Step 1: Create a developer account
Go be able to publish apps to the FORMIDE platform, you need to have a developer account. To create an account, log into FORMIDE.com and go to settings -> account. Here you can click the 'request developer account' button to enable developer mode on your account. After a short while, you will receive an email confirming your developer status and you're ready to publish your first app!

### Step 2: Create a new app entry
To create a new app entry, go do developers.formide.com and go to the 'my apps' page.
Besides the app itself, we would like to have some information about your app before publishing it, like the name, the category, an awesome icon that represents what your app is and does and a small description that users can read before using the app. To get people to use your app, try to make all of these as attractive as possible!

### Step 3: Build and upload your app
To upload the actual app, you need to download our CLI (Command Line Interface) tools so you can push your app code from your computer to our platform. If you have node.js and NPM installed already, installing the FORMIDE CLI is really easy. Run the following command to install the CLI:

```
npm install -g formide-cli
```

Then you can login to FORMIDE using the CLI tools so that you can test and publish app versions:

```
formide-cli login
```

After that, you can create a new app by running:

```
formide-cli init
```

This will create a new folder and add some default files based on the user input given after running this command. Based on these files, you can build out your app. One of the inputs is the unique app ID that is needed to identify your app. When you created your app on developers.formide.com, the app ID was generated and was showed on the app page. Copy this ID and paste it when the CLI asks for it.

You can use HTML, CSS and JavaScript without restrictions to functionality. Once uploaded to the platform, we run your app in a separate window or sandboxed environment, so no access to platform code is possible.

When you're happy with your app, you can test it locally by running the following command inside the root folder of your app:

```
formide-cli run
```

This will insert an access token in the browser window that's running the app so you can actually upload the resulting 3D file of your app to your FORMIDE account to test if it prints well.

The final step to upload your app is running the publish command. This uploads a new version of your app (automatically bumps the current version number by 1 patch, please do this manually if you prefer a different version increase) to the platform ready to be published:

```
formide-cli publish
```

This command will give some output depending if the upload succeeded or not (like information about missing mandatory files).

### Step 4: Publish your app!
It's time for the last step: publishing your app! Go to the 'my apps' page on developers.formide.com and select the app you created before. Now you will see an entry under versions, this is the app you just uploaded. To set a version as the active (published) version, just click the 'public' button behind the version number. Now your app is published on the platform, ready for everyone to use!

### Step 5: Analyze and improve
We gather some data of the users that are using your app, including number of usages, number of exported 3D files and number of prints actually made from these files. We anonymize this data and show this in your app settings. This data can help you to improve your app so it gives better results when printing a model from it. In the future, we will also add the option to leave comments for each print made so you can get more detailed information about how users experience your app and the printed results.
