---
Modules have a certain file structure and can use internal api's to connect to other (core) modules and the outside world.

> This manual does not go in to detail on JavaScript, Node.js, express or any of the other frameworks used in the FORMIDE client. Please familiarise yourself with these before reading this manual and creating your first module.

---
### File structure

#### package.json
The package.json file is required to configure and load modules via NPM. They also contain module specific settings.

```
{
  "name": "formideos-module-webhook",
  "version": "1.0.26",
  "description": "WebHook module for FORMIDE client",
  "main": "index.js",
  "repository": {
    "type": "git",
    "url": "https://github.com/PRINTR3D/formideOS-module-webhook.git"
  },
  "keywords": [
    "FORMIDE",
    "webhook"
  ],
  "author": "Chris ter Beke <chris@printr.nl>",
  "license": "GPLv2",
  "bugs": {
    "url": "https://github.com/PRINTR3D/formide-client-webhook/issues"
  },
  "homepage": "https://github.com/PRINTR3D/formide-client-webhook",
  "dependencies": {
    "request": "^2.57.0"
  },
  "devDependencies": {}
}
```

#### config.json
You can use the config.json to store static configuration items for your module like a port number or if your HTTP endpoints should be protected. The config is accessible in FORMIDEOS using the internal config API and is inserted in the `init()` function of your module.

```
{
    "port": "1338",
    "permission": true
}
```

#### index.js
The index.js file is the main file of your module. Small modules can have their logic in this file, larger modules can required needed files that the logic is placed in. The index.js file has 3 reserved functions: `setup()`, `init()` and `exposeSettings()`. They are not required but we advise to use them to your advantage.

```
var request = require('request');
module.exports = {
    
    // this function is called when FORMIDE loads your module
    setup: function() {
        console.log('hi, im loaded!');
    }
    
    // this function is called when FORMIDE activates your module
    init: function (config) {
        console.log('hi, im activated!');
        
        FormideOS.events.on('log.error', this.call.bind(this));
    },
    
    // this function should return a javascript array with valid setting objects for this module
    exposeSettings: function() {
        
        var moduleSettings = [];
        
        moduleSettings.push({
            name: "url",
            label: "URL",
            type: "text",
            default: "https://myUrl.com/post?key=1234567",
            required: true
        });
        
        moduleSettings.push({
            name: "method",
            label: "Method",
            type: "select",
            default: "POST",
            options: [
                {
                    name: "GET",
                    label: "GET",
                },
                {
                    name: "POST",
                    label: "POST",
                }
            ],
            required: false
        });
        
        return moduleSettings;
    },

    call: function(data) {
        
        // example payload formatted for Slack
        var payload = {
            text: data.data,
            username: data.message
        };
        
        if (!FormideOS.settings.get('formide-client-webhook', 'url')) {
            FormideOS.debug.error('Webhook URL not set!', true);
        }

        request.post({
            method: FormideOS.settings.get('formide-client-webhook', 'method') || "POST", // whatever user put in here or default to POST
            uri: FormideOS.settings.get('formide-client-webhook', 'url'), // whatever user put in here
            form: JSON.stringify(payload)
        }, function(error, response, body) {
            if (error) {
                FormideOS.debug.log('Could not send to webhook', true);
    		}
        });
    }
}
```

#### api.js
The api.js file exposes your module's HTTP api. The routes will be available after the `http://YOUR_LOCAL_IP:1337/api/MODULE_NAME/` path. This part of your module should be a full Express sub-app.

```
module.exports = function(routes, module) {
    
    // routes is an express instance, module is the instance of your module that FORMIDEOS loaded
    // notice the permission check via the clients internal http API
    routes.get('/test', FormideOS.http.permissions.check('webhook:test'), function(req, res, next) {
        module.call({
            data: "Test webhook call",
            message: "This call is done to test the remote webhook url. If you see this, it worked!"
        });
        return res.send('OK');
    });
};
```

---
### APIs
For a full list of internal APIs, check the [api](#/api) section.