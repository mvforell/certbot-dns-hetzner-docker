# certbot-dns-hetzner-docker
Dockerfile for a certbot image with the certbot-dns-hetzner plugin installed.

Intended to be used in scripts, e. g.
```
docker run --rm \
        -v /var/lib/letsencrypt:/var/lib/letsencrypt -v /etc/letsencrypt:/etc/letsencrypt \
        --cap-drop=all \
        mvforell/certbot-dns-hetzner certonly \
        --authenticator dns-hetzner --dns-hetzner-propagation-seconds 900 \
        --dns-hetzner-credentials /var/lib/letsencrypt/hetzner_credentials.ini \
        --no-self-upgrade --keep-until-expiring --non-interactive --expand \
        --server https://acme-v02.api.letsencrypt.org/directory \
        -d "<YOUR DOMAIN HERE>"
```
See also [here](https://github.com/ctrlaltcoop/certbot-dns-hetzner).
