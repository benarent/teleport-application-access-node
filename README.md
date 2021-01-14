# Teleport Application Access Node.js JWT Example App

Teleport can be used to secure access to internal dashboards and applications. This
sample application provides automatic access using JSON Web Tokens (JWTs). This
application restricts access to a specific Teleport Proxy. Once logged in, it'll
show the Teleport roles available to the application.

Prerequisites
- A Teleport Cluster running 5.1.0 or greater.
    - Teleport Cloud [Signup](https://goteleport.com/get-started/)
    - Teleport self-hosted [quickstart](https://goteleport.com/teleport/docs/quickstart/)
- Node.js local environment with Teleport running locally _or_ quickly [use this template](https://github.com/benarent/teleport-application-access-node/generate) and [deploy to Heroku](https://heroku.com/deploy)

### Configuring the App:
- Update .env `TELEPORT_PROXY` with the public address and port of your Teleport Cluster

### Run it locally:

1. Clone this repo, install and run the app.
```bash
npm install
TELEPORT_PROXY=example.teleport.sh:443 node ./app.js
```

2. [Install Teleport](https://goteleport.com/teleport/docs/installation/) locally, in this setup Teleport will dial back to Teleport Cloud.

Start Teleport:
```bash
# Update --auth-server to your Teleport Cloud account
teleport start --roles=app --auth-server=example.teleport.sh:443 \
    --app-name="jwt-quickstart" \
    --app-uri="http://localhost:8080"
```

### Run this app on Heroku:

1. Clone with [Github Template](https://github.com/benarent/teleport-application-access-node/generate)
2. Update .env `TELEPORT_PROXY` with the public address and port of your Teleport Cluster
3. Deploy to Heroku. Quickly Deploy using
    - [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)
    - This Application will now be at https://_heroku-app-name_.herokuapp.com
4. Proxy Traffic to the Application.
    - Self hosted users can update `teleport.yaml`
        ```yaml
        # Snippet if using teleport.yaml
        #...
        app_service:
            enabled: yes
            debug_app: yes
            apps:
            - name: "jwt-quickstart"
                uri: "https://_heroku-app-name_.herokuapp.com"
        ```
    - Teleport Cloud users can ... (How to Proxy with Heroku using Teleport Cloud...maybe needs a custom buildpack.)
