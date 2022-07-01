---
sidebar_position: 1
---

# Portainer
Portainer is a container management tool.

## Upgrading portainer

To update portainer you first have to stop the container using:
``` sh
docker stop portainer
```

Remove the container:
``` sh
docker rm portainer
```

> Dont worry about the data, this is stored in a docker volume

Then pull the latest image:
``` sh
docker pull portainer/portainer-ce:latest
```

Then run the new container:
``` sh
docker run -d -p 8000:8000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
