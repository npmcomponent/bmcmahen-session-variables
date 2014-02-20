*This repository is a mirror of the [component](http://component.io) module [bmcmahen/session-variables](http://github.com/bmcmahen/session-variables). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/bmcmahen-session-variables`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# session-variables

  Persistent session variables for maintaining an application state inbetween user sessions. I'm using this for a mobile app so that I can record a user's application state and restore it when the user reloads the page, closes the app, etc.

## Installation

  Install with [component(1)](http://component.io):

    $ component install bmcmahen/session-variables

## API

### Session()

Create a new session variables instance.

### set(key, value, options)

Set a key to a value, emitting a `change:key` event. Options: `{ silent: true}` to silence emitter events and `{ noStore: true }` to avoid using localstorage for that particular setter.

### get(key)

Return the current value of the key.

### unset(key)

Unset a key, emitting a `change:key` event.

### clear()

Clear all of the current session variables.

### setDefault(key, value, options)

Sets the key to value, only if that key has not been set. This is useful when restoring an application state from localstorage. Options are the same as for `set`.

### restore()

Retrieves all values from localstorage, and populates your session variables.


## Example

	var Session = require('session-variables');
	var session = new Session();
	session.on('change:layout', function(value, previousValue){
		// render my layout.
	});
	session.setDefault('layout', 'browse');


## License

  MIT
