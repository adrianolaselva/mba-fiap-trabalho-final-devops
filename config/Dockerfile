FROM bitnami/jenkins:latest

RUN apt-get update -y
RUN apt-get install software-properties-common -y

RUN echo deb http://http.debian.net/debian jessie-backports main >> /etc/apt/sources.list
RUN apt-get update
RUN apt install -t jessie-backports  openjdk-8-jre-headless ca-certificates-java -y
RUN apt-get install openjdk-8-jre -y
RUN apt-get install openjdk-8-jdk -y
RUN update-alternatives --config java
RUN echo 'JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre' >> ~/.bashrc
RUN echo 'JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre' >> ~/.bashrc

RUN echo 'JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre' >> /etc/environment
RUN echo 'JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre' >> /etc/environment

RUN curl -O http://www-us.apache.org/dist/maven/maven-3/3.5.4/binaries/apache-maven-3.5.4-bin.tar.gz
RUN tar xzvf apache-maven-3.5.4-bin.tar.gz
RUN mkdir /opt/maven
RUN mv apache-maven-3.5.4/* /opt/maven
RUN echo 'PATH=/opt/maven/bin:/usr/lib/jvm/java-8-openjdk-amd64/jre/bin:$PATH' >> ~/.bashrc
