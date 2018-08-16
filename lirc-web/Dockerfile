# The base image is not actually available on Docker hub, built using the
# Dockerfile available at
# https://github.com/resin-io-library/base-images/blob/176f303398167828e95438719849ea6dfa39ddde/node/raspberrypi3/debian/8.11/stretch/Dockerfile
# found in
# https://github.com/resin-io-library/official-images/blob/master/library/raspberrypi3-node
# linked from Resin's Docker Hub page:
# https://hub.docker.com/r/resin/raspberrypi3-node/
FROM resin/raspberrypi3-node:8.11-stretch

LABEL maintainer="John Fisher"
RUN apt-get update && apt-get install -y \
    lirc \
 && rm -rf /var/lib/apt/lists/*

# Create directory for PID files.
RUN mkdir -p /var/run/lirc

RUN npm install -g lircv0.9.4_web@v1.0.1

CMD lircd && lircv0.9.4_web
