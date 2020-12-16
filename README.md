# Node.js example application

This is an example of Node.js application that restricts access using a Teleport Application Access feature.

Run it:

```bash
npm install
TELEPORT_PROXY=asteroid-sun.teleport.sh:443 node ./app.js
```

For testing purposes, if you have a self-signed certificate you could also pass `TELEPORT_INSECURE=true` environment variable
