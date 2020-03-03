On your local machine, 4 VMs will be created and finally will join docker swarm cluster and run one application with 3 replicas.

Result
=======
```bash
To add a manager to this swarm, run '' and follow the instructions.

vagrant@manager-1:~$ docker stack ls
NAME                SERVICES            ORCHESTRATOR
app                 1                   Swarm
vagrant@manager-1:~$ docker service ls
ID                  NAME                MODE                REPLICAS            IMAGE               PORTS
doiyd8zuwtmw        app_app             replicated          3/3                 nasabayat/app:01    *:8080->8080/tcp
vagrant@manager-1:~$ docker service ps app_app
ID                  NAME                IMAGE               NODE                DESIRED STATE       CURRENT STATE           ERROR               PORTS
ny12va2nw9zy        app_app.1           nasabayat/app:01    manager-2           Running             Running 3 minutes ago                       
woemlq2wmb9s        app_app.2           nasabayat/app:01    manager-3           Running             Running 3 minutes ago                       
zfajzo05cgjy        app_app.3           nasabayat/app:01    manager-1           Running             Running 3 minutes ago                       
vagrant@manager-1:~$ docker node ls
ID                            HOSTNAME            STATUS              AVAILABILITY        MANAGER STATUS      ENGINE VERSION
vdsqoz9zoknsq7lkg0k7lveev *   manager-1           Ready               Active              Leader              19.03.6
yb6ei5wmzhzk1avmbuja930mr     manager-2           Ready               Active              Reachable           19.03.6
sqowj4id6ixx33k5te3pwvc6q     manager-3           Ready               Active              Reachable           19.03.6
reb7h5guqao8p0eadk5s37l88     worker-1            Ready               Active                                  19.03.6
```

Requirements
==============

* Ansible
* Vagrant 1.6 or newer (1.5 may work, too; 1.4 does not)
* Virtualbox
* git clone https://github.com/nasabayat/genscape.git

- localhost is used as hosts
- user which Virtualbox installed with it, should be used

# DevOps Challenge Problem

Members of the DevOps team are responsible for operations, configuration management, automated deployments, and monitoring.

The following problem is an opportunity to demonstrate your knowledge in these areas and perhaps learn something along the way.

## Your challenge

1. **Configuration Management**: Using the latest Ubuntu LTS, write the necessary [ansible](https://www.ansible.com/) playbook to:
   1. Build a Docker Swarm Cluster with three masters servers (you can use [vagrant](https://www.vagrantup.com/) to achieve it).

   2. Apply best practices to make the server secure.

2. **Application**: the application exposes the port `:8080`, and there are the two endpoints: `/work` and `/metrics`. The `work` endpoint just return `OK` response, and it did not expect any input. The `/metrics` endpoint exposes Prometheus metrics. You will find the application in the [application](./application) directory.

   1. Containerize the application. The app is a simple binary ready to go.
   2. Use [docker stack](https://docs.docker.com/engine/reference/commandline/stack/) to deploy the application in the cluster.
   3. Apply best practices to build the docker image and deployment.
   4. It seems that the developer had a bad day, so the app has an easter egg, can you find it?

3. **Have fun!** Feel free to add your own features and ideas so long as they complement and extend the required features. This is your chance to show off.
