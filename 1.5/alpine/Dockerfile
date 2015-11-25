#
# DesertBit Golang GB Dockerfile
#

FROM golang:1.5-alpine

MAINTAINER Roland Singer, roland.singer@desertbit.com

ENV PROPATH /project
ENV PATH $PROPATH/bin:$PATH

RUN mkdir -p "$PROPATH" && chmod -R 777 "$PROPATH"
WORKDIR $PROPATH

# Install dependencies.
RUN apk add --update git && \
	rm -rf /var/cache/apk/*

# Install gb.
RUN go get github.com/constabulary/gb/... && \
	go install github.com/constabulary/gb

# Remove the unneeded dependencies again.
RUN apk del git && \
	rm -rf /var/cache/apk/*
