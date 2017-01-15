# Caddy Docker Image

A minimalistic Docker image for Caddy.

    $ docker run -d \
      -v $HOME/caddy/Caddyfile:/etc/caddy/Caddyfile \       (1)
      -v $HOME/caddy/crypto:/etc/caddy/crypto \             (2)
      -p 80:80 -p 443:443 \
      blachniet/caddy
      
**1)** By default, this image expects to find the Caddyfile in `/etc/caddy/Caddyfile`.
You can use this line to mount your own `Caddyfile` at this location.

**2)** **This is strongly suggested in order to avoid Let's Encrypt rate limits**.
This image sets the `CADDYPATH` to `/etc/caddy/crypto`. This is where [caddy stores
certificates and private keys](https://caddyserver.com/docs/automatic-https#the-caddy-folder).
You can persist these across container runs this line.
`-v $HOME/caddy/crypto:/etc/caddy/crypto`.

## Included Features

- Server
  - [ ] DNS
  - [X] HTTP
- Directives/Middleware
  - *none*
- DNS Providers
  - *none*