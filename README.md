# slackcord.css

A dark themed slack stylesheet.

## Sidebar Theme

Best used with the following Sidebar Theme settings:

```
#2e3136,#282b30,#282b30,#ffffff,#282b30,#818386,#43b581,#7289da
```

## Installation

Open the following file based on your platform:

- Linux:
    - `/usr/lib/slack/resources/app.asar.unpacked/src/static/ssb-interop.js`
- Windows:
    - `%LocalAppData%\Slack\<version>\resources\app.asar.unpacked\src\static\ssb-interop.js`
    - Replace `version` with the installed slack version
- Mac:
    - `/Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static/ssb-interop.js`

Append the following to the end of the file:

```javascript
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/Galkon/slackcord.css/master/style.css',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```
