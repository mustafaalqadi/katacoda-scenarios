## Manage Docker as a non-root user

The Docker daemon binds to a Unix socket instead of a TCP port. By default that Unix socket is owned by the user root and other users can only access it using sudo. The Docker daemon always runs as the root user.

If you don’t want to preface the docker command with sudo, create a Unix group called docker and add users to it. When the Docker daemon starts, it creates a Unix socket accessible by members of the docker group.

To create the docker group and add your user:

<pre>Create the docker group.</pre>

`sudo groupadd docker`{{execute}}

<pre> Add your user to the docker group.</pre>

`sudo usermod -aG docker $USER`{{execute}}

Log out and log back in so that your group membership is re-evaluated.

If testing on a virtual machine, it may be necessary to restart the virtual machine for changes to take effect.

On a desktop Linux environment such as X Windows, log out of your session completely and then log back in.

<pre>On Linux, you can also run the following command to activate the changes to groups:</pre>

`newgrp docker`{{execute}}

<pre>Verify that you can run docker commands without sudo.</pre>

`docker run hello-world`{{execute}}

## Configure Docker to start on boot

Most current Linux distributions (RHEL, CentOS, Fedora, Debian, Ubuntu 16.04 and higher) use systemd to manage which services start when the system boots. On Debian and Ubuntu, the Docker service is configured to start on boot by default. To automatically start Docker and Containerd on boot for other distros, use the commands below:

`sudo systemctl enable docker.service`{{execute}}
`sudo systemctl enable containerd.service`{{execute}}