---
## HTTP
The HTTP utility will come in handy when you want to add HTTP api endpoints to your module. To do this, you can simply create an api.js in your module's root with the following contents:

```
module.exports = function(routes, module) {
    
    // routes is an express instance, module is the instance of your module that FORMIDEOS loaded
    // notice the permission check via FormideOS.http.permissions.check
    routes.get('/', FormideOS.http.permissions.check('webhook:test'), function(req, res, next) {
        
    });
};
```

The example above has a GET route for /. This means that the module's root endpoint will serve whatever will be in this endpoint function. The root endpoint of your module is constructed out of the API root of your FORMIDEOS instance (http://my_ip:1337) + /api + /my_module. So for a module called webhook running locally, this would be http://localhost:1337/api/webhook.

---
### Routes
The routes parameter that is injected in your module is an Express.router() instance. This means you can do whatever Express allows you to do in their router.

---
### Module functions
To call a function defined in the index.js of your module, you can simple call that fucntion using the module variable that is injected in your api file.

```
module.exports = function(routes, module) {
    
    // routes is an express instance, module is the instance of your module that FORMIDEOS loaded
    // notice the permission check via FormideOS.http.permissions.check
    routes.get('/', FormideOS.http.permissions.check('webhook:test'), function(req, res, next) {
        module.myCustomFunction();
    });
};
```