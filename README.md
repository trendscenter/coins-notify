# coins-notify
show notifications in the browser. attempts to use 'growl' like notifications first, but falls back on notifyjs (jQuery plugin) if the browser user has not accepted (or has denied) growl like notifications.

# usage
Note: if jQuery fallback is being used, jQuery && [notifyjs](http://notifyjs.com/) must be loaded onto the window.  This module does **not** address those dependencies.

```js
var Notify = require('coins-notify');
var notifier = new Notifier();

// show a notification
notifier.push({
    body: 'test!',
    className: 'info'
});
```

# api
## Notify(opts) [constructor]
### opts
*type: object*
- `maxQueue` *number* number of messages to internally retain history over.  not persistent accross browser sessions. See `notifyInstance.queue` for history


## push(opts)
### opts
*type: object*

- `body`* *string* text shown in notification body
- `className` *string* class name applied.  Supported classNames are those supported in [notifyjs](http://notifyjs.com/) (alt mode only)
- `alt`/`alternative`/`fallback` *boolean* force the notifier to use the notifyjs fallback
- `icon` *string* absolute url to icon (default mode only)
- `tag` *string* tag!
- `timeout` *number* ms [default, 5000], duration for notification to stay up
- `notifyShow` *function* callback
- `notifyClose` *function* callback
- `notifyClick` *function* callback
- `notifyError` *function* callback