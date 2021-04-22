# test-docker-jenkins

simple example jenkins + dind container + private registry

preinstall steps: 
docker and docker-compose should be installed

how to run:

1. run `docker-compose up -d --build`
2. on localhost:8080 you will find jenkins instance
3. find example job for build docker image and push to local registry - job name 'simpledockerjob'

----
installation details:
- jenkins image build on start from `jenkins-docker/Dockerfile`
- plugins list also may be changed in `jenkins-docker/plugins.txt`
- all configuration in casc config (for CASC plugin). Inin job 'simpledockerjob' too.
- setup wizard is disabled by default ('ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false' in Dockerfile)
- dind container used for build docker image, docker cli installed in jenkins master image
- registry available on localhost:5000

----
limitations and possible improvements
- add admin password  (removed due simple start)
- move docker cli to additional tools (instead package on master)
- docker registry is insecure, need a valid cert 
