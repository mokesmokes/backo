# backo2

  Simple exponential backoff because the others seem to have weird abstractions. It's based on [backo](https://github.com/segmentio/backo). Difference is that this one exposes setter methods on the instance: `setMin`, `setMax` and `setJitter`.  

## Installation

```
$ npm install backo2
```

## Options

 - `min` initial timeout in milliseconds [100]
 - `max` max timeout [10000]
 - `jitter` [0]
 - `factor` [2]

## Example

```js
var Backoff = require('backo2');
var backoff = new Backoff({ min: 100, max: 20000 });

setTimeout(function(){
  something.reconnect();
}, backoff.duration());

// later when something works
backoff.reset()
```

# License

  MIT
