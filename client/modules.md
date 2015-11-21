---
The FORMIDE client is built in modules. Each module is registered in the client and can expose internal functions, an HTTP api, a WebSocket API or connect to other local running services.

![formideos_scheme](https://raw.githubusercontent.com/PRINTR3D/documentation/master/client/img/formideos_scheme.png)

We distinguish between core modules and 3rd party modules. Core modules are all the modules that the client should have for every install. Removing or disabling these modules will break FORMIDEOS. The names of these modules are also reserved, so you can't publish a module with the same unique name.

3rd party modules are all the modules that you, the developers, create for the client. You can host them on any public Git repository or npmjs.org (Node Package Manager) and include them in the OS via NPM install.

> Please note that modules are in their very beginnings. At this point, they can crash the client or are not compatible with each other. In the future we'll add a repository to browser for modules as well.

![formideos_module_settings](https://raw.githubusercontent.com/PRINTR3D/documentation/master/client/img/formideos_module_settings.png)

---

### Popular modules

[formide-client-webhook](https://github.com/PRINTR3D/formide-client-webhook)
<br/>
Send a message with a body to a remote url (webhook) when an error is triggered in formide-client.

[formide-client-camerapi](https://github.com/PRINTR3D/formide-client-camerapi)
<br/>
Output a video stream from your printer so you can watch along remotely.
