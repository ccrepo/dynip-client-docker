# Dockerfile

# Use the official Ubuntu 22.04 base image
FROM ubuntu:22.04

# Environment
ARG DYNIP_DOCKER_GITUSER=default_value

# Info
RUN bash -c "echo starting using github user ${DYNIP_DOCKER_GITUSER} "

# Install apt-utils
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y apt-utils && \
    rm -rf /var/lib/apt/lists/*

# Install necessary build tools for C++
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y openjdk-19-jdk && \
    rm -rf /var/lib/apt/lists/*

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y git gradle curl wget openssl net-tools && \
    rm -rf /var/lib/apt/lists/*

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y build-essential && \
    rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /usr/local/src

# Clone dynip-server
RUN git clone https://github.com/${DYNIP_DOCKER_GITUSER}/dynip-client.git

# Set the working directory
WORKDIR /usr/local/src/dynip-client/bin

# Build
RUN ./c

RUN mkdir -p /usr/local/src/dynip-client/src/main/sh/server

RUN echo user > /usr/local/src/dynip-client/src/main/sh/server/credentials

RUN echo -n password >> /usr/local/src/dynip-client/src/main/sh/server/credentials

# Expose the default Tomcat port
EXPOSE 8080

# Start when the container starts
ENTRYPOINT ["tail", "-f", "/dev/null"]
