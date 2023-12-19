# Configure an NGINX Proxy with an Internal, Self-Hosted Tier.run Instance on Fly.io

This repository builds on @gordalina's [fly-tier](https://github.com/gordalina/fly-tier) to allow you to stand up an 
NGINX proxy in front of your private, hosted [tier.run](https://www.tier.run/) (RIP) instance on Fly.io.
This may be useful in case your app is hosted on another platform (like Vercel), but you want to use Fly.io for your self-hosted Tier instance.

## Setup

- Follow the instructions in [fly-tier](https://github.com/gordalina/fly-tier) to deploy your internal, hosted Tier instance

## Deploy NGINX Proxy

1) Clone this repository

2) Use the fly launch command to detect the Dockerfile in this repo, build it, and then deploy your app.
Ideally you should select the same region as your hosted Tier instance. Make sure you use the default port (8080).

```sh
fly launch
```

3) If you make any changes to the nginx.conf, you can redeploy with:

```sh
fly deploy
```

4) Your new TIER_BASE_URL is now available at `https://<proxy-name>.fly.dev`.
