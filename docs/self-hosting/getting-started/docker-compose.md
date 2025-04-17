# docker compose

### Overview

Docker Compose uses environment variables to customize container configurations. These variables can be defined in multiple ways to support different deployment scenarios.



### Env file

The [.env](https://vscode-file/vscode-app/Applications/Visual%20Studio%20Code%20-%20Insiders.app/Contents/Resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) file is a key-value file placed in the same directory as your [docker-compose.yaml](https://vscode-file/vscode-app/Applications/Visual%20Studio%20Code%20-%20Insiders.app/Contents/Resources/app/out/vs/code/electron-sandbox/workbench/workbench.html). It contains environment variables that will be loaded by Docker Compose.

#### Example [.env](https://vscode-file/vscode-app/Applications/Visual%20Studio%20Code%20-%20Insiders.app/Contents/Resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) file:

{% @github-files/github-code-block url="https://github.com/atomic-blend/backend/blob/main/.env.example" %}

### Required Environment Variables

The following environment variables are required:

#### Env

* `ENV` : the env of the project (dev / prod)

#### Database

* `DATABASE_NAME` : The name of the database

#### SSO

* `SSO_SECRET`: Secret to generate and sign JWT Secrets

#### Firebase (optional)

* `GOOGLE_APPLICATION_CREDENTIALS`: The path of the google JSON credentials to use Firebase (for notifications)
* `FIREBASE_PROJECT_ID`: The project ID of the Firebase Project

