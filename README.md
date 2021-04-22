# test-docker-jenkins

simple example jenkins + dind container + private registry

preinstall steps: 
docker and docker-compose should be installed

how to run:

1. run `docker-compose up -d --build`
2. on localhost:8080 you will find jenkins instance (password you can find in container log (`docker-compose exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword`))
3. find example job for build docker image and push to local registry - job name 'simpledockerjob'


