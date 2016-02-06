---
### DevKit
We made developing for FORMIDE extremely easy and intuitive with our dedicated development kit! One click publishing, version management and sdk injection are just a few of the really handy features that allow you to start on your content immediately instead of managing your code.

We're updating the development kit all the time, and upcoming features include GIT integration, local project management, code linting and more settings.

---

### Overview
This interactive overview shows the most important functionality of the development kit. Hover on the dots to see some information about that particular module.

<section style="position: relative;">
    <a href="#" class="tooltip" data-tooltip="Filetree" style="left: 70px; top: 100px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Upload app" style="left: 170px; top: 4px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Preview app" style="left: 210px; top: 4px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Open app manager" style="left: 250px; top: 4px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Your current project's name" style="left: 370px; top: 4px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Upload state and version" style="left: 450px; top: 4px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Login and account info" style="left: 600px; top: 4px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="An open file tab" style="left: 300px; top: 40px;"><span class="tooltip__bullet"></span></a>
    <a href="#" class="tooltip" data-tooltip="Add a new file or folder" style="left: 40px; top: 410px;"><span class="tooltip__bullet"></span></a>
    <img src="./public/assets/images/devkit_example.png" alt="Devkit Dark Example">
</section>
<br/>

---

### Editors
The development kit has multiple editors that get selected depending on the filetype. Most files will be opened using the CodeMirror javascript code editor. The app.json file opens in a nice manifest editor with input fields. STL files will be opened in our own 3D viewer, which is the same one that is available in the 3D api. In a future release, this will also allow you to edit your 3D file before adding it to your app.

---

### CLI tools
Want to use your own programming environment? No problem! Just download the CLI tools from NPM (npm install -g formide-cli) and you're ready to go directly from your terminal window. More info and documentation can be found at github.com/PRINTR3D/formide-cli.