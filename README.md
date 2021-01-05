# Teleport Application Access Node.js JWT Example App

Teleport can be used to secure access to internal dashboards and applications. This
sample application provides automatic access using JSON Web Tokens (JWTs). This
application restricts access to a specific Teleport Proxy. Once logged in, it'll
show the Teleport roles available to the application.

Prerequisites
- A Teleport Cluster running 5.1.0 or greater.
- Node.js local environment or quickly [use this template](https://github.com/benarent/teleport-application-access-node/generate) and [deploy to Heroku](https://heroku.com/deploy)

Configuring the App:
- Update .env `TELEPORT_PROXY` with the public address of your Teleport Cluster

Run it locally:

```bash
npm install
TELEPORT_PROXY=example.teleport.sh:443 node ./app.js
```

Run it on Heroku:
