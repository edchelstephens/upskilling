# Kubernetes

# Created by Google

- The nam kubernetes, it's greek for helmsman or captain
- The helmsman, being the person who steers the ship

also pronounced as "k8s", basically replacing the 8 letters between "k" and "s"
in kubernetes, hence "k8s"

# While docker is for low level stuff, kubernetes is for high level stuff like:

- How many containers to run in
- which nodes to run them on
- knowing when to scale them up and down
- how to update your containers without downtime

- Kubernetes is like the conductor of an opera
- wherein the opera different musics, like drums, singers, are the containerized apps
- Kubernetes basically issues commands to docker instances, telling them
  when to start and stop containers and how to run them. And just like the opera,
  when all these things come together, they form this amazing application experience.

# We tell Kubernetes what we want, and kubernetes makes it happen

Then when things change, increased load, failed nodes, kubernetes deals with it.

- Docker's doing all the low-level container spinning up, spinning down stuff,
  but it only does it when Kubernetes tells it to. Meaning in this respect,
  Kubernetes is managing a bunch of Docker nodes.

# Kubernetes is all about managing containerized apps at scale and the focus is very much on the app.

- It's the poster child for the [Cloud Native Computing Foundation](https://www.cncf.io/), the leading foundation driving the development and adoption of Cloud Native Technologies.
