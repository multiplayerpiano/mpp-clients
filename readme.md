# API

## Install

`yarn add mpp-clients`

## Usage

```typescript
import {BrowserClient} from 'mpp-clients/browserClient/BrowserClient'
// For server
// import {ServerClient} from 'mpp-clients/serverClient/ServerClient'
import {Action} from 'mpp-clients/actions'

const Client = BrowserClient; // or ServerClient

const start = async () => {
  const client = new Client(); // by default `{url: 'https://multiplayerpiano.com'}`
  
  // add listener before you connect to don't lose any actions.
  client.on(action => {
    if(action.type === Action.hi) {
      // do something
      console.log(action.payload)
    }
  })

  // Will send `client.send({type: 'hi'})`. @todo: we should wait for a server ack so we are sure that are connected.
  // Will throw an error if can't connect, so you need a try/catch
  await client.connect();

  // This will send a `request` type of action. Is not guaranteed that your action will be accepted by the server.
  // After that the server will emit an action back to client if has been successful or failed.
  client.send({type: 'note', payload: {/* Note arguments */}});

  await client.disconnect();
}

start();

```


## Typescript Types

Import all `Action` types available in mpp.

```
import {Action} from 'mpp-clients/actions'
```

@todo: maybe `mpp-clients/actions` should be in another project so can be shared on server side.
