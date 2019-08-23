# DevOps Challenge Problem

Members of the DevOps team are responsible for operations, configuration management, automated deployments, and monitoring.

The following problem is an opportunity to demonstrate your knowledge in these areas and perhaps learn something along the way.

## Your challenge

1. **Configuration Management**: Using the latest Ubuntu LTS, write the necessary [ansible](https://www.ansible.com/) playbook to:
   1. Build a Docker Swarm Cluster with three masters servers (you can use [vagrant](https://www.vagrantup.com/) to achieve it).

   2. Apply best practices to make the server secure.

2. **Application**: the application exposes the port `:8080`, and there are the two endpoints: `/work` and `/metrics`. The `/metrics` endpoint exposes Prometheus metrics. You will find the application in the [application](./application) directory.

   1. Containerize the application. The app is a simple binary ready to go.
   2. Use [docker stack](https://docs.docker.com/engine/reference/commandline/stack/) to deploy the application in the cluster.
   3. Apply best practices to build the docker image and deployment.
   4. The application has an easter egg, can you find it?

3. **Have fun!** Feel free to add your own features and ideas so long as they complement and extend the required features. This is your chance to show off.
