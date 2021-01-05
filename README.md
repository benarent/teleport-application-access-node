# Node.js example application

This is an example of Node.js application that restricts access using a Teleport
Application Access feature. This example app requires Teleport Version 5.0.3 or greater.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)


Run it:

```bash
npm install
TELEPORT_PROXY=asteroid-sun.teleport.sh:443 node ./app.js
```

For testing purposes, if you have a self-signed certificate you could also pass
`TELEPORT_INSECURE=true` environment variable
