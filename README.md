# Teleport Application Access Node.js JWT Example App

Teleport can be used to secure access to internal dashboards and applications. This
sample application provides automatic access using JSON Web Tokens (JWTs). This
application restricts access to a specific Teleport Proxy. Once logged in, it'll
show the Teleport roles available to the application.

Prerequisites
- A Teleport Cluster running 5.1.0 or greater.
- Node.js local environment or quickly deploy this template to Heroku [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

Configuring the App:
- Set `TELEPORT_PROXY`

Run it:

```bash
npm install
TELEPORT_PROXY=example.teleport.sh:443 node ./app.js
```

Other:
For testing purposes, if you have a self-signed certificate you could also pass
`TELEPORT_INSECURE=true` environment variable
