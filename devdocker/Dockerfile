FROM debian:jessie
MAINTAINER Davis Kirkendall <davis.e.kirkendall@gmail.com>

RUN apt-get -y update
RUN apt-get -y install wget git libfontconfig wget adduser openssl ca-certificates gcc build-essential libssl-dev pkg-config curl
RUN mkdir /code
WORKDIR /code
RUN wget https://storage.googleapis.com/golang/go1.5.2.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.5.2.linux-amd64.tar.gz
RUN rm go1.5.2.linux-amd64.tar.gz
ENV PATH /usr/local/go/bin:$PATH

# sd
ENV GOPATH "/code"
RUN go get github.com/Unknwon/bra
# RUN go get github.com/daviskirk/grafana
# WORKDIR $GOPATH/src/github.com/daviskirk/grafana
# RUN go run build.go setup
# RUN $GOPATH/bin/godep restore
# RUN go run build.go build

# install nodejs, npm and frontend libraries
RUN curl -sL https://deb.nodesource.com/setup_5.x | bash -
RUN apt-get install -y nodejs
RUN npm install -g grunt-cli
RUN npm install

RUN apt-get clean
EXPOSE 3000
