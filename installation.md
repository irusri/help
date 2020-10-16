# Installation

GenIE-Sys can be installed in a few different methods as below.

{% tabs %}
{% tab title="Docker installation" %}
[Docker](https://www.docker.com/) is a software that provides the ability to package and run an application in an isolated environment called a container.

```text
# With docker-compose 
git clone https://github.com/irusri/docker4geniesys.git  
cd docker4geniesys  
docker-compose up

************** OR **************

# Without docker-compose 
git clone https://github.com/irusri/docker4geniesys.git  
cd docker4geniesys  
docker build -t genie -f ./Dockerfile .  
docker run --rm -i -t -p "80:80" -p "3308:3306" -v ${PWD}/genie:/app -v ${PWD}/mysql:/var/lib/mysql -e MYSQL_ADMIN_PASS="mypass" --name genie genie  
cd genie 
```

When we need to commit changes, please go to `cd docker4geniesys/geniesys` folder. Never commit from `docker4geniesys` folder. Because it will add genie as a submodule. Incase you mistakenly pushed from `docker4geniesys` folder, please `cd docker4geniesys` and `git rm genie`. You can access MySQL using `mysql -u admin -pmypass -h localhost -P 3308` or using [phpMyAdmin](http://localhost/phpmyadmin). Some useful docker commands are as follows.

```text
# Must be run first because images are attached to containers
docker rm -f $(docker ps -a -q)
# Delete every Docker images
docker rmi -f $(docker images -q)
# To see docker process
docker ps -l 
# To see or remove all volumes
docker volume ls/prune
# To run bash inside the running docker container
docker exec -it 890fa15eeef6126b668f4b0fcb7a38b33eaff0 /bin/bash
or
docker attach 890fa15eeef6126b668f4b0fcb7a38b33eaff0
```
{% endtab %}

{% tab title="With XAMP/MAMP" %}

{% endtab %}
{% endtabs %}

