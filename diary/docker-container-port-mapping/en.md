---
title: Docker Container Port Mapping
date: '2020-12-06'
tags:
  - docker
  - container
  - port
category:
  slug: devops
  title: Devops
seo:
  title: Docker Container Port Mapping
  description: Publish a container’s port(s) to the host
---

[port-mapping]: /diary/docker-container-port-mapping/port-mapping.svg
[docker-run]: /diary/docker-container-port-mapping/docker-run.svg

In Docker, anytime that someone makes a request to a given port on your local network, it takes that request
automatically and forwards it to a port inside the container. This is only about incoming requests. The docker container
can by-default make requests on its own behalf to the outside world. An example for this is when you install a
dependency. So there is no limitation for outgoing requests.

---

![Container Port Mapping][port-mapping]

The port forwarding is not defined inside the Dockerfile as it's strictly a run time constraint. In other words, it’s
something that we only change when we run a container or start a container.

![Docker Run][docker-run]

The `docker run` command initially creates a writeable container layer over the specified image, and then starts it using
the specified command. We use `--publish` or `-p` flag to make a port available to services outside of Docker, or to
Docker containers which are not connected to the container’s network. So this command will publish a container’s port
`8080` to the host with port `4000`. In the other words, considering `4000:8080`, the left one is the port in host network
which is your machine and the right one is the port in internal container network. If you change the port inside the
container, you need to make sure that your actual application is listening to that port number.

Similarly, you can map a port inside a docker compose file. Taking `hello` project as an example in a compose file:

```yaml
# localhost:4000 from host network - your machine
# hello:8080 from guest - internal docker network
services:
  hello:
    ports:
      - 4000:8080/tcp
```

A dash in YML file represents an array. So we can technically map many different ports inside of a single docker compose
file too for a single service or a single container.
