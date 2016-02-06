---
## Config
The config utily keeps track of all static configuration in FORMIDEOS and all modules. In config, no user data is stored. That is done in the settings utility, which is meant for dynamic setting storage. Each module's config is added to the global config when a module is loaded. This means you cannot change module config items during runtime, but only after a module is unloaded and then loaded again.

---
### Functions

```
// You can get configuration items by dot seperated keys. 
FormideOS.config.get('myModule.configItem');

// You can get the current development environment name using config.environment.
FormideOS.config.environment();
```