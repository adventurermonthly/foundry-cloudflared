# foundry-cloudflared

Forked from [davebenvenuti/foundry-cloudflared](https://github.com/davebenvenuti/foundry-cloudflared)- a simple [FoundryVTT](https://foundryvtt.com) + [Cloudflare Tunnel](https://www.cloudflare.com/products/tunnel/) setup.

## Setup

### Docker Compose

You should have [docker compose](https://docs.docker.com/compose/) installed either through [docker desktop](https://docs.docker.com/desktop/) or [docker engine](https://docs.docker.com/engine/).

### Cloudflare

You should have a cloudflare account (free) and you should [create a tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/get-started/) (also free at the time of writing this).

When creating the tunnel, you can use `foundry:30000` for the hostname.  This will work for any foundry instances set up with this docker compose file, including multiple running on the same machine.

Be sure to keep your tunnel token handy from setting up a cloudflare tunnel.

## Environment Variables

create `./env.d/cloudflared` and `./env.d/foundry` and populate them with

### env.d/cloudflared
```
TUNNEL_TOKEN=
```

where

TUNNEL_TOKEN - the token for your cloudflare tunnel

### env.d/foundry
```
FOUNDRY_PASSWORD=           
FOUNDRY_USERNAME=
FOUNDRY_ADMIN_KEY=
CONTAINER_PRESERVE_CONFIG=true
```
where 

- FOUNDRY_PASSWORD - your password for https://foundryvtt.com/.           
- FOUNDRY_USERNAME - your username for https://foundryvtt.com/
- FOUNDRY_ADMIN_KEY - *set* your admin password here

### docker-compose.yml 

You will also want to add a volume and pin a version in the docker-compose.yml file.  See the inline comments for guidance.

