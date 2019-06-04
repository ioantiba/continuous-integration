# continuous-integration
Continuous Integration Tools

#Build docker-compose containers
docker-compose -f integration.yml up --build --force-recreate

#Up and down containers
docker-compose -f integration.yml up | down


1.
Attaching to jenkins
jenkins    | touch: cannot touch '/var/jenkins_home/copy_reference_file.log': Permission denied
jenkins    | Can not write to /var/jenkins_home/copy_reference_file.log. Wrong volume permissions?

R:
sudo chown -R 1000 /storage/development/docker/volumes/continuous-integration/jenkins/


2.
ERROR Unable to create file /opt/sonarqube/logs/es.log java.io.IOException: Permission denied

R:
sudo chown -R 999 /storage/development/docker/volumes/continuous-integration/sonarqube/
