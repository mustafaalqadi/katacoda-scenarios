
## Uninstall old versions

Older versions of Docker were called docker, docker.io, or docker-engine. If these are installed, uninstall them:

`sudo apt-get remove docker docker-engine docker.io containerd runc`{{execute}}

## Set up the repository

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

<pre>Update the apt package index and install packages to allow apt to use a repository over HTTPS:</pre>

`sudo apt-get update`{{execute}}

`sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release`{{execute}}

 <pre>Add Docker’s official GPG key:</pre>

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`{{execute}}

<pre>Use the following command to set up the stable repository</pre>

`echo \ "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
`{{execute}}


## install docker engine:

<pre>Update the apt package index, and install the latest version of Docker Engine and containerd </pre>

`sudo apt-get update`{{execute}}
`sudo apt-get install docker-ce docker-ce-cli containerd.io`{{execute}}

<pre>Verify that Docker Engine is installed correctly by running the hello-world image.</pre>

`sudo docker run hello-world`{{execute}}
