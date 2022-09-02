# ansible-kong-module
A Module to help manage a [Kong](http://getkong.com) API Gateway

**Requirements**

* Ansible
* python requests library
* Docker and Docker Compose

**Quickstart**

From a Docker-enabled terminal run:

```
git clone git@github.com:henrygultom/ansible-kong-module.git && cd ansible-kong-module
docker-compose up
```

This might take a while to run ... after it is finished you can find the IP of your docker machine with:

```
$ docker-machine ip default
> 1.2.3.4
```
(assuming your docker-machine is called default). 

You can then access your Kong API at: 

* **Admin interface:** 1.2.3.4:8001 
* **REST Interface:** 1.2.3.4:8000 


**Configure your Kong instance with:**

```
ansible-playbook playbook.yml -i inventory --extra-vars "kong_admin_base_url=1.2.3.4:8001 kong_base_url=1.2.3.4:8000"
```

* set kong_admin_base_url and kong_base_url to your Kong instance's urls
