# NCALayerJS

A small wrapper around [NCALayer](https://pki.gov.kz/en/ncalayer-2/) websocket API.

## Installation

```sh
npm install @seithq/ncalayer
```

or

```sh
yarn add @seithq/ncalayer
```

## Usage

```javascript
import Client from "@seithq/ncalayer"

// Initialize websocket connection with running NCALayer.
let ws = new WebSocket("wss://127.0.0.1:13579/")

// Handle onopen, onerror and onclose events as you want.
ws.onopen = (e) => {
  // your code goes here
}

ws.onerror = (e) => {
  // your code goes here
}

ws.onclose = (e) => {
  // your code goes here
}

// Initialize client to work with API.
const client = new Client(ws)

// Call API method.
client.browseKeyStore("PKCS12", "P12", "", (data) => {
  // on success
  if (data.isOk()) {
    // some action
  }

  // on failure
  console.error(data)
})
```

## Demos

- [React](https://github.com/seithq/ncalayer-react)
- [Stimulus](https://github.com/seithq/ncalayer-stimulus)

## Maintainers

[@danikarik](https://github.com/danikarik)

## License

This project is licensed under the [MIT License](LICENSE).
