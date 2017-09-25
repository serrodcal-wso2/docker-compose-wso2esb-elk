FROM airdock/oracle-jdk:jdk-1.8

RUN apt-get update && \
    apt-get install -y zip wget vim filebeat && \
    wget -P /opt https://s3-us-west-2.amazonaws.com/wso2-stratos/wso2esb-5.0.0.zip && \
    apt-get clean && \
    unzip /opt/wso2esb-5.0.0.zip -d /opt && \
    rm /opt/wso2esb-5.0.0.zip

# Add the carbon application
ADD target/echoApp_1.0.0.car /opt/wso2esb-5.0.0/repository/deployment/server/carbonapps/echoApp_1.0.0.car

EXPOSE 9443 8243 8280
WORKDIR /opt/wso2esb-5.0.0
CMD ["bin/wso2server.sh"]