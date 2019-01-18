There is a javascript file you must modify in order to use the dark theme.

1. Right click on Slack in your applications folder and select `Show Package Contents`.
1. Then go to `Contents > Resources > app.asar.unpacked > src > static > ssb-interop.js`.
1. Open it with your preferred code editor.
1. Add the code snippet into that file at around line 16.
    ```js
    // Slack dark style override. Add this to ssb-interop.js at about
    // line 16 (after the `const allowedChildWindowEventMethod`)
    document.addEventListener('DOMContentLoaded', function() {
     $.ajax({
      url:
       'https://raw.githubusercontent.com/liamross/slack-night-mode/master/css/raw/black.css',
      success: function(css) {
       $('<style></style>')
        .appendTo('head')
        .html(css);
      }
     });
    });
    ```
