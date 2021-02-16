ARG DEBIAN_VERSION=stable-slim

# Sonatype Nexus Ahab Evaluation
FROM debian:${DEBIAN_VERSION} as ahab
RUN apt-get update && apt-get install -y ca-certificates curl
WORKDIR /tmp/ahab
RUN curl -o ahab -O -L RUN curl -o ahab -O -L https://github.com/sonatype-nexus-community/ahab/releases/download/v0.2.3/ahab-linux.amd64-v0.2.3

RUN chmod +x ahab
RUN update-ca-certificates

FROM tomcat:7
ARG IQ_TOKEN
ARG IQ_USER
ARG IQ_SERVER
ARG IQ_STAGE

# Sonatype Nexus Ahab Evaluation
COPY --from=ahab /tmp/ahab /tmp/
RUN dpkg-query --show --showformat='${Package} ${Version}\n' | /tmp/ahab chase

RUN set -ex \
	&& rm -rf /usr/local/tomcat/webapps/* \
	&& chmod a+x /usr/local/tomcat/bin/*.sh

COPY target/struts2-rest-showcase.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
