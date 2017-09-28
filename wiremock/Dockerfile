FROM airdock/oracle-jdk:jdk-1.8

ENV WIREMOCK_VERSION 2.6.0

# grab wiremock standalone jar
RUN apt-get update && \
    apt-get install -y zip wget vim && \
  	mkdir -p /var/wiremock/lib/ && \
  	wget https://repo1.maven.org/maven2/com/github/tomakehurst/wiremock-standalone/${WIREMOCK_VERSION}/wiremock-standalone-$WIREMOCK_VERSION.jar -O /var/wiremock/lib/wiremock-standalone.jar && \
  	apt-get clean

EXPOSE 8080 8081

WORKDIR /home/wiremock

CMD ["java", "-cp", "/var/wiremock/lib/*:/var/wiremock/extensions/*", "com.github.tomakehurst.wiremock.standalone.WireMockServerRunner"]