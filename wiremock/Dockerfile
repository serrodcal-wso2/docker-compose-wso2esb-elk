FROM airdock/oracle-jdk:jdk-1.8

ENV WIREMOCK_VERSION 2.6.0

RUN apt-get update && \
    apt-get install -y zip wget vim && \
	curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-5.6.2-amd64.deb && \
    chmod 777 filebeat-5.6.2-amd64.deb && \
    sudo dpkg -i filebeat-5.6.2-amd64.deb && \
    rm filebeat-5.6.2-amd64.deb && \
    apt-get clean

# grab wiremock standalone jar
RUN mkdir -p /var/wiremock/lib/ \
  && wget https://repo1.maven.org/maven2/com/github/tomakehurst/wiremock-standalone/${WIREMOCK_VERSION}/wiremock-standalone-$WIREMOCK_VERSION.jar \
    -O /var/wiremock/lib/wiremock-standalone.jar

EXPOSE 8080 8081

WORKDIR /home/wiremock

CMD ["java", "-cp", "/var/wiremock/lib/*:/var/wiremock/extensions/*", "com.github.tomakehurst.wiremock.standalone.WireMockServerRunner"]