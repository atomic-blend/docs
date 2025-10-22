# docker compose

## Overview

Docker Compose uses environment variables to customize container configurations. These variables can be defined in multiple ways to support different deployment scenarios.

## Deploy Atomic Blend via docker-compose

1. Clone the `backend` repository locally:
```
git clone https://github.com/atomic-blend/backend.git atomic-blend-backend
cd atomic-blend-backend/docker
```

There's a script named `ab-manager.sh` that will take care of:
- fetching the latest version of each components on the GitHub Container Registry (requires GitHub PAT)
- create .env and docker-compose.yaml if not present
- update .env with the latest version fetched for each components
- help you set-up the necessary configurations to run Atomic Blend (public domain, ...)

2. Run the `ab-manager.sh` script:
```
export GITHUB_TOKEN="ghp_xxxxxxxxxxxxxxxxxxxxxxxxxx"
./ab-manager.sh
```

The script will show you:

1. Missing files
```
Missing files that need to be downloaded:
  - .env.example → /root/atomic-blend-backend/docker/.env

Repository: atomic-blend/backend
Branch: main

Enter 'y' or 'yes' to download missing files: y
```

2. Check for latest versions
```
Checking for latest versions...

IMAGE                                    CURRENT         LATEST          STATUS
---------------------------------------- --------------- --------------- ----------
auth                                     latest          0.12.0          OUTDATED
mail-server                              latest          0.3.0           OUTDATED
mail                                     latest          0.3.0           OUTDATED
productivity                             latest          0.12.1          OUTDATED
task-app                                 latest          0.13.1          OUTDATED
notes-app                                latest          0.4.1           OUTDATED
mail-app                                 latest          0.3.0           OUTDATED

Summary:
==========
Add these to your .env.versions file:

AUTH_SERVICE_VERSION=0.12.0
MAIL_SERVER_SERVICE_VERSION=0.3.0
MAIL_SERVICE_VERSION=0.3.0
PRODUCTIVITY_SERVICE_VERSION=0.12.1
TASK_APP_VERSION=0.13.1
NOTES_APP_VERSION=0.4.1
MAIL_APP_VERSION=0.3.0

Would you like to automatically update the .env file with these new versions?
Enter 'y' or 'yes' to proceed: y
```

3. Configure Atomic Blend
```
Would you like to configure atomic-blend settings?
Enter 'y' or 'yes' to proceed:

Environment Configuration
=========================

SSO_SECRET is empty or missing. Generating a new one...
Updated SSO_SECRET with newly generated value

Public Domain Configuration
============================
PUBLIC_ADDRESS and ACCOUNT_DOMAINS define where your service will be accessible.

Current value: atomic-blend.com
Example: app.example.com

Would you like to update the public domain? (y/n): y
Enter public domain: brandonguigo.com
Updated PUBLIC_ADDRESS to brandonguigo.com
Added ACCOUNT_DOMAINS="brandonguigo.com"


User Account Limit Configuration
==================================
AUTH_MAX_NB_USER defines the maximum number of user accounts allowed.

Current value: 10

Would you like to update the maximum number of users? (y/n): n
Skipped AUTH_MAX_NB_USER configuration.

Script completed successfully!
```


4. Start the platform
```
docker compose up -d
```