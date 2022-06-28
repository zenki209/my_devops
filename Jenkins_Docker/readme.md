Run the command below for running docker

docker run --name jenkins -d \
  --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 \
  -p 8080:8080 -p 50000:50000 \
  -v /src/devops/jenkins_home:/var/jenkins_home \
  -v /src:/src \
  -v docker-certs-jk:/certs/client:ro \
  blackkoala/koala-jenkins-docker:latest

Getting Password
➜  jenkins git:(main) ✗ docker exec -it d5 bash
jenkins@d5609c0f9f69:/$ cat /var/lib/jenkins/secrets/initialAdminPassword