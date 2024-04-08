# ansible-network-automation


## Netbox
### Netbox
```bash
$ cd netbox-docker

$ tee docker-compose.override.yml <<EOF
version: '3.4'
services:
  netbox:
    ports:
      - 8000:8080
EOF

$ docker compose pull
$ docker compose up

$ docker compose exec netbox /opt/netbox/netbox/manage.py createsuperuser
```

### Device type library
```bash
$ export NETBOX_TOKEN=<your_netbox_token>

$ docker run --add-host host.docker.internal:host-gateway -e "NETBOX_URL=http://host.docker.internal:8000/" -e "NETBOX_TOKEN=<your_netbox_token>" ghcr.io/minitriga/netbox-device-type-library-import
``
