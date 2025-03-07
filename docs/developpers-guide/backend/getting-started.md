# Getting Started

## Fork & Clone the repo

Fork, then clone the repository



## Configuring the env

Copy `.env.example.com` to `.env` &#x20;

Generate the secret value for SSO using:&#x20;

```shellscript
openssl rand 256 | base64 -w0
```

## Launching the API

There's a Dockerfile that includes all the necessary containers to run Atomic Blend backend

Install docker and run:

```
docker-compose up -d
```

The API, DB and all the required stuff should start.



## Hot Reload

The API will hot reload at every code change automatically.
