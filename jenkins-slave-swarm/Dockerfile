FROM docker:18.05

MAINTAINER Martin Kvapil <martin@qapil.cz>

ENV JENKINS_SWARM_VERSION 3.13
ENV HOME /var/jenkins_home

RUN apk --update add openjdk8-jre git \
	&& mkdir -p /usr/share/jenkins \
	&& chmod 755 /usr/share/jenkins

RUN wget -O /usr/share/jenkins/swarm-client-$JENKINS_SWARM_VERSION.jar https://repo.jenkins-ci.org/releases/org/jenkins-ci/plugins/swarm-client/$JENKINS_SWARM_VERSION/swarm-client-$JENKINS_SWARM_VERSION.jar

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

VOLUME /var/jenkins_home

ENTRYPOINT ["/entrypoint.sh"]
