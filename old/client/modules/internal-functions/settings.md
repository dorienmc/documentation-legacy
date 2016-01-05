---
## Settings manager
This module manages the global user settings of FORMIDEOS.

---
FormideOS.settings.get(moduleName[ ,settingName])

```
var webhookURL = FormideOS.settings.get('formideos-module-webhook', 'url');
```

---
FormideOS.settings.set(moduleName, settingName, newValue)

```
FormideOS.settings.set('formideos-module-webhook', 'url', 'https://hooks.slack.com/my/webhook/url');
```

---
FormideOS.settings.getTarget()

```
var fullSettings = FormideOS.settings.getTarget();
```