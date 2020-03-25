FROM openjdk:8u242-buster

RUN apt-get update
RUN apt-get install -y sudo
RUN apt-get install -y apt-utils

RUN \
    echo "TRYING TO INSTALL SBT" && \
    echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list && \
    curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add && \
    apt-get update && apt-get install sbt

RUN sbt -version
RUN java -version

WORKDIR /the/workdir/path

RUN ./install.sh