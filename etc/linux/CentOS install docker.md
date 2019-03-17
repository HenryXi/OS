#CentOS install docker
It is easy to install docker in CentOS. Open the official website of docker copy commands and paste them in your terminal.
now docker only support CentOS7+. Before installing you need make sure your CentOS version is higher than 7.
For the detail you can click [here](https://docs.docker.com/install/linux/docker-ce/centos/)
1. set up the repository
```
$ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
2. install docker ce
```
$ sudo yum install docker-ce docker-ce-cli containerd.io
```
3. start docker
```
$ sudo systemctl start docker
```
4. verify 
```
$ sudo docker run hello-world
```
You have installed docker successfully if you can see following output.
```
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete 
Digest: sha256:2557e3c07ed1e38f26e389462d03ed943586f744621577a99efb77324b0fe535
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

EOF
