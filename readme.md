## EventEmitter

**EventEmitter** Library for **Google Apps Script** ([GAS]).

This library to create and handle custom events. The EventEmitter class can be used to create and handle custom events module.

## ID Library

- Legacy: `MVu2RaHxeCsJkOyDmPEUqHaZTb1melOAr`
- New: `1cEe0m2gnWKt-IQx5nUwV4_Hb9KVu5R3W9LmRfw2pfhK0li_1ewAITRZZ`

## Start

```javascript
const eventEmitter = new EventEmitter.init();
```

## Example

### Start

```javascript
const event = new EventEmitter.init();

event.on('start', () => {
  Logger.log('started')
})

event.emit('start');
```

### Arguments

```javascript
const event = new EventEmitter.init();

event.on('start', number => {
  console.log(`started ${number}`)
})

event.emit('start', 23);
```

### Multiple Arguments

```javascript
const event = new EventEmitter.init();

event.on('start', (start, end) => {
  console.log(`started from ${start} to ${end}`)
})

emit('start', 1, 100);
```

### Extends

```javascript
class myEvent extends EventEmitter.init {
    constructor() {
        super();
    }

    /*
    ... your code
    */
};

const event = new myEvent();

event.on('start', number => {
  console.log(`started ${number}`)
})

event.emit('start', 23);
```

### Remove Listener

```javascript
const event = new EventEmitter.init();

const callback = () => {
  Logger.log('someone connected!');
};
// register
event.on('connection', callback);
// remove it
event.off('connection', callback);
```

### Count

```javascript
const event = new EventEmitter.init();

event.on('start', () => Logger.log(1) );
event.on('start', () => Logger.log(2) );

let count = (event.listenerCount('start');
Logger.log('count', count);

```


## Methods

Available now

- **on(events, ... listeners)** Adds the listener function to the end of the listeners array for the event named `event`. No checks are made to see if the `listener` has already been added. Multiple calls passing the same combination of eventName and listener will result in the listener being added, and called, multiple times.
- **emit(event, ...args)**  calls each of the `listeners` registered for the event named `event`, in the order they were registered, passing the supplied arguments to each.
- **addListener(event, listener)** add single event
- **once(event, listener)** Adds a one-time listener function for the event named `event`. The next time `event` is triggered, this listener is removed and then invoked.
- **off(event, listener)** Removes the specified listener from the listener array for the event named `event`
- **listenerCount(event)** Returns the number of listeners listening to the event named `event`.


[Telegram]: https://www.telegram.org
[GAS]: https://developers.google.com/apps-script
[@botindonesia]: https://t.me/botindonesia