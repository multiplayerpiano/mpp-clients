# API

## Install

`yarn add mpp-clients`

## Usage

```
import {BrowserClient} from 'mpp-clients/browserClient/BrowserClient'
// For server
// import {ServerClient} from 'mpp-clients/serverClient/ServerClient'

const client = BrowserClient; // or ServerClient

const client = new Client(); // by default `{url: 'https://multiplayerpiano.com'}`

// Will send `client.send({type: 'hi'})`. @todo: we should wait for a server ack so we are sure that are connected.
client.connect()

client.send({type: 'note', payload: {/* Note arguments */}})

client.disconnect()
```


## Typescript Types

Import all `Action` types available in mpp.

```
import {Actions} from 'mpp-clients/Actions'
```
