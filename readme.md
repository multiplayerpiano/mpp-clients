# API

## Install

`yarn add mpp-clients`

## Usage

```typescript
import {BrowserClient} from 'mpp-clients/browserClient/BrowserClient'
// For server
// import {ServerClient} from 'mpp-clients/serverClient/ServerClient'

const client = BrowserClient; // or ServerClient

const start = async () => {
  const client = new Client(); // by default `{url: 'https://multiplayerpiano.com'}`

  // Will send `client.send({type: 'hi'})`. @todo: we should wait for a server ack so we are sure that are connected.
  // Will throw an error if can't connect, so you need a try/catch
  await client.connect();

  client.send({type: 'note', payload: {/* Note arguments */}});

  await client.disconnect();
}

start();

```


## Typescript Types

Import all `Action` types available in mpp.

```
import {Actions} from 'mpp-clients/Actions'
```
