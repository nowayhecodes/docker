FROM debian:jessie

RUN \
    echo "--> Trying to install Java 8" && \
    echo "--> Adding Jessie backports " && \
    echo "deb http://http.debian.net/debian jessie-backports main" | tee /etc/apt/sources.list && \
    apt-get update && apt-get install jessie-backports openjdk-8-jre && \
    java -version

RUN \
    echo "--> Adding Scala SBT repository..." && \
    echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list && \
    curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | apt-key add && \
    apt-get update && \
    apt-get install sbt

# RUN ./install.sh

CMD ["java"]