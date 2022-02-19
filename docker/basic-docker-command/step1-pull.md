pull is an argument to download the docker image from the docker registry, its similar to git repository but designed to store the docker images than the code.
By default, the docker command will pull the image from DockerHub. When you do a pull, if the tag/version is not given for an image, the docker daemon assumes 
the **latest** tag by default.

`docker pull ubuntu`{{execute}}

<pre>Using default tag: latest
latest: Pulling from library/ubuntu
d72e567cc804: Pull complete 
0f3630e5ff08: Pull complete 
b6a83d81d1f4: Pull complete 
Digest: sha256:bc2f7250f69267c9c6b66d7b6a81a54d3878bb85f1ebb5f951c896d13e6ba537
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest</pre>

You will see the following output for the **docker pull** command. If you wish, you can hide the output with an extra argument called 
**--quiet** or **-q**.

`docker pull -q alpine`{{execute}}

<pre>docker.io/library/alpine:latest</pre>

