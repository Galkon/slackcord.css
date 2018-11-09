# slackcord.css

A dark themed slack stylesheet.

## Sidebar Theme

Best used with the following Sidebar Theme settings:

```
#2f3136,#42464D,#3a3d42,#f6f6f7,#3A3D42,#969ba3,#43b581,#f04747
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

:warning: WARNING: This will request the compiled CSS file from this repository.
You are strongly discouraged from using a remote CSS file that is not under your
control. It's recommended that you create your own copy. An XSS attack could put
your Slack client at risk.

## Known Issues

There are many problem areas still, but the basic chat experience is pretty smooth. If you feel like contributing, just use Chrome developer tools to alter the CSS and copy that over and make a pull request.

Components not yet optimized for slackcord theme:

* Modals
* Context menus
* Settings
* Dropdown inputs
* Rich embeds
* Search
* Right sidebar
