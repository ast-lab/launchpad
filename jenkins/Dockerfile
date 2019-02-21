FROM docker/compose:1.23.2 as compose
FROM jenkins/jenkins:lts-slim

COPY --from=compose /usr/local/bin/docker /usr/local/bin/docker
COPY --from=compose /usr/local/bin/docker-compose /usr/local/bin/docker-compose

USER root
RUN echo "docker:x:999:jenkins" >> /etc/group

USER jenkins
