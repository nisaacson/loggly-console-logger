# Loggly Console Logger

[![Dependency Status](https://david-dm.org/nisaacson/loggly-console-logger.png)](https://david-dm.org/nisaacson/loggly-console-logger)

Winston-based logger that outputs to the console and loggly if the loggly input token is set in the nconf object


# Installation

```bash
npm install -S loggly-console-logger
```

# Usage

To use send your logs to loggly, you must first specify your `inputToken` and `subdomain` in the nconf object.  Only logs with the level `info` and higher will be sent to loggly. Any `debug` level logging statements are only logged to the console


```javascript
var nconf = require('nconf').argv().env().defaults({
  loggly: {
    inputToken: 'foo-loggly-input-token-here',
    subdomain: 'foo'
  }
})

var logger = require('logger')
logger.debug('this will be logged to the console only')
logger.info('this will be logged to the console and submitted to loggly as well')
```


