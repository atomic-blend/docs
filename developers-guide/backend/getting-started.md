---
icon: play
---

# Getting Started

## Fork & Clone the repo

Fork and clone the [backend repository](https://github.com/atomic-blend/backend)

Switch to the "dev" branch

## Configuring the env

Copy `.env.example.com` to `.env` &#x20;

Set the value of SSO_SECRET by generating a secret using:&#x20;

```shellscript
openssl rand 256 | base64 -w0
```

## Launching the API

*docker-compose-dev.yaml* includes all the necessary instructions to run Atomic Blend's backend

Install docker and run:

```
docker compose -f docker-compose-dev.yaml up -d
```

The API, DB and all the required stuff should start.



## Hot Reload

The API will hot reload at every code change automatically.
