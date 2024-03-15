# Stap 1
Alle packages downloaden via deze link https://download.docker.com/linux/debian/dists/
Proxmox 8 gebruikt bookworm, dan pool/stable/amd64.
```bash
wget https://download.docker.com/linux/debian/dists/bookworm/pool/stable/amd64/containerd.io_1.6.26-1_amd64.deb
```
```bash
wget https://download.docker.com/linux/debian/dists/bookworm/pool/stable/amd64/docker-ce_24.0.7-1~debian.12~bookworm_amd64.deb
```
```bash
wget https://download.docker.com/linux/debian/dists/bookworm/pool/stable/amd64/docker-ce-cli_24.0.7-1~debian.12~bookworm_amd64.deb
```
```bash
wget https://download.docker.com/linux/debian/dists/bookworm/pool/stable/amd64/docker-buildx-plugin_0.11.2-1~debian.12~bookworm_amd64.deb
```
```bash
wget https://download.docker.com/linux/debian/dists/bookworm/pool/stable/amd64/docker-compose-plugin_2.21.0-1~debian.12~bookworm_amd64.deb
```

# Stap 2
Packages installeren, vervang de namen door de correcte namen van de packages
```bash
dpkg -i ./containerd.io_<version>_<arch>.deb \
  ./docker-ce_<version>_<arch>.deb \
  ./docker-ce-cli_<version>_<arch>.deb \
  ./docker-buildx-plugin_<version>_<arch>.deb \
  ./docker-compose-plugin_<version>_<arch>.deb
```

# Stap 3
Controleer of docker werkt
```bash
service docker start
docker run hello-world
```
Verwachte uitvoer:
```bash
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
c1ec31eb5944: Pull complete 
Digest: sha256:ac69084025c660510933cca701f615283cdbb3aa0963188770b54c31c8962493
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```