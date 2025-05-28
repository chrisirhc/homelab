# homelab

My random homelab configurations.

To update a container, first `cd` into the directory for that container.
```bash
# https://stackoverflow.com/a/56687449/315562
cd homeassistant
docker-compose pull
docker-compose up --detach
```

To restart a container:
```bash
docker-compose restart
```
