# API

```
import {BrowserClientV1} from 'mpp-clients/browserClientV1'

const client = new BrowserClientV1({url: 'https://multiplayerpiano.com'});

// Will send `client.send({type: 'hi'})`. @todo: we should wait for a server ack so we are sure that are connected.
client.connect()

client.send({type: 'note', payload: {/* Note arguments */}})

client.disconnect()
```
