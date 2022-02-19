**run** is an argument to start a container from the docker image. There are a lot of options that we can use, such as a name for the container, bind port, and so on.

For example, we can run a container in the background using **-d** option and give it a name using **--name** option.

`docker run -d --name myubuntu ubuntu`{{execute}}

The container will start/run in the background, but if you list the containers with **docker ps**, you won’t find the container with **myubuntu** name.

CONTAINER ID        IMAGE           COMMAND          CREATED          STATUS           PORTS            NAMES

Why? Because there is no process attached to the container so it will exit as soon as it starts with the status **exited**. To keep the container running, we can add the **--interactive** or **-i** argument.

`docker run -d --name myubuntu -i ubuntu`{{execute}}

If you run the above command, it will raise an error as we are using the same container name as before.

<pre>docker: Error response from daemon: Conflict. The container name "/myubuntu" is already in use by container "4b48e0e1e5266cf59ee9004d4df6127931e6100b7a2269bdbdf559da9a836384". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.</pre>

How do we fix this? We can run the **docker rm** command to remove the previous container.

`docker rm myubuntu`{{execute}}

Let’s re-run the myubuntu interactive command.

`docker run -d --name myubuntu -i ubuntu`{{execute}}

<pre>c43190a11b8a68673a49f967d78da11cc4d27c3222fedb6496395f4e175ac807</pre>

Lets run **docker ps** command to see if myubuntu container is still running or not.

CONTAINER ID        IMAGE            COMMAND             CREATED             STATUS                  PORTS            NAMES
7aca537e07e2        ubuntu           "/bin/bash"         2 seconds ago       Up Less than a second                    myubuntu

As you can see, the container is still running.

# Run a command in a running container

**exec** is an argument to execute a command inside a container or to get the shell in the container.

`docker exec myubuntu whoami`{{execute}}

<pre>root</pre>

`docker exec myubuntu cat /etc/lsb-release`{{execute}}

<pre>DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=20.04
DISTRIB_CODENAME=focal
DISTRIB_DESCRIPTION="Ubuntu 20.04.1 LTS"</pre>

Or you can also spawn a shell in the container.

`docker exec -it myubuntu bash`{{execute}}

<pre>root@c43190a11b8a:/#</pre>

As you can see, we are dropped into a bash shell. Let’s exit out of it using **exit** command.
`Exit`{{execute}}



