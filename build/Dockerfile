# syntax=docker/dockerfile:1.4

FROM --platform=$BUILDPLATFORM httpd as builder

# Install useful tools and install important libaries
RUN apt-get -y update && \
apt-get -y --no-install-recommends install nano wget && \
apt-get install -y iputils-ping && \
apt-get -y --no-install-recommends install --fix-missing apt-utils \
build-essential \
git \  
curl \
zip \
openssl && \
rm -rf /var/lib/apt/lists/*