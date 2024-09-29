## Docker PHP MySQL Setup

### Docker installation

```bash
# update the package manager and install some prerequisites (all of these aren't technically required)
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common libssl-dev libffi-dev git wget nano

# create a group named docker and add yourself to it
#   so that we don't have to type sudo docker every time
#   note you will need to logout and login before this takes affect (which we do later)
sudo groupadd docker
sudo usermod -aG docker ${USER}

# add Docker key and repo
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# update the package manager with the new repos
sudo apt-get update

# upgrade the distro
sudo apt-get upgrade -y
sudo apt-get autoremove -y

# install docker
sudo apt-get install -y docker-ce containerd.io

# (optional) install latest version of docker compose
sudo curl -sSL https://github.com/docker/compose/releases/download/`curl -s https://github.com/docker/compose/tags | \
grep "compose/releases/tag" | sed -r 's|.*([0-9]+\.[0-9]+\.[0-9]+).*|\1|p' | head -n 1`/docker-compose-`uname -s`-`uname -m` \
-o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose

```

- [Install Docker on WSLv2 (Ubuntu)](https://dev.to/bartr/install-docker-on-windows-subsystem-for-linux-v2-ubuntu-5dl7)
- [Setting Up PHP Development Environment with Docker](https://www.sitepoint.com/docker-php-development-environment/)
- [Dockerizing a Laravel App](https://dev.to/kamruzzaman/dockerizing-a-laravel-app-nginx-mysql-phpmyadmin-and-php-82-43ne)

- [How To Install Composer](https://www.digitalocean.com/community/tutorials/how-to-install-composer-on-ubuntu-20-04-quickstart)
- [How to Install the Latest PHP on WSL](https://www.allurcode.com/how-to-install-the-latest-php-version-on-windows-subsystem-for-linux-wsl/)
- [WSL2 PHP Dev](https://github.com/enflow/wsl2-php-development)
