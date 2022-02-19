
**ps** is an argument to list containers (running form of images). It provides various options to filter the output according to the status of the container like created, running, exited, or stopped etc.

Let’s run a container that exits and see if **-a** options shows us the container’s status.

`docker run -d --name yourubuntu ubuntu`{{execute}}

Now, check the status using **docker ps -a** option.

`docker ps -a`{{execute}}

CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
7aca537e07e2        ubuntu              "/bin/bash"         4 minutes ago       Up 4 minutes                            myubuntu
9ebd1d8e6d84        debian              "bash"              5 minutes ago       Exited (0) 5 minutes ago                       sleepy_hellman

As you can see, the above output shows all containers of status included, exited, or stopped.
What happens if you use th above command without **-a**?

# Show the running processes of a container

**top** is an argument to display the running processes inside a container.

`docker top myubuntu`{{execute}}

UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                1336                1318                0                   19:16               ?                   00:00:00            /bin/bash

As you can see, **myubuntu** container is running bash process.

# Challenge

1.	How can you run the nginx container in the background?
2.	Give the container a name such as webserver and add any environment variables into it
3.	Don’t forget to bind container port to the host as port 80 so you can access it through this  
If you are struggling with exercises, please refer the hints

(https://docs.docker.com/engine/reference/commandline/run/#set-environment-variables--e---env---env-file)
(https://docs.docker.com/engine/reference/commandline/run/#publish-or-expose-port--p---expose)

# Additional Resources

For more information about Docker commands, see the following references:
•	(https://docs.docker.com/engine/reference/commandline/pull)
•	(https://docs.docker.com/engine/reference/commandline/run)
•	(https://docs.docker.com/engine/reference/commandline/exec)
•	(https://docs.docker.com/engine/reference/commandline/ps)
