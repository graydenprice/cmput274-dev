FROM ubuntu:22.04

# Change Working Directory
WORKDIR /usr/src/app

# Install Dependencies

RUN apt-get -y update && apt-get -y install

# begin installing GCC
RUN apt-get -y install build-essential wget zlib1g-dev libssl-dev openssl ssh

# begin installing python
RUN wget https://www.python.org/ftp/python/3.8.10/Python-3.8.10.tgz
RUN tar xzvf Python-3.8.10.tgz
RUN ./Python-3.8.10/configure
RUN make
RUN make install

RUN apt-get -y remove wget zlib1g-dev libssl-dev openssl
RUN apt-get -y update && apt-get -y install

# Copy requirements.txt From Host
COPY .devcontainer/requirements.txt .

# Install Requirements
RUN pip3 install pygame
# RUN pip install --no-cache-dir -r requirements.txt
