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

### Device typ library
```bash
docker run -e "NETBOX_URL=http://localhost:8000/" -e "NETBOX_TOKEN=d692257431518d900fe45a661d9977fd2677b4b1" ghcr.io/minitriga/netbox-device-type-library-import

docker run --add-host host.docker.internal:host-gateway -e "NETBOX_URL=http://host.docker.internal:8000/" -e "NETBOX_TOKEN=<your_netbox_token>" ghcr.io/minitriga/netbox-device-type-library-import
``
