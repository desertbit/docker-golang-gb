#
# DesertBit Golang GB Dockerfile
#

FROM golang:1.7

MAINTAINER Roland Singer, roland.singer@desertbit.com

ENV PROPATH /project
ENV PATH $PROPATH/bin:$PATH

RUN mkdir -p "$PROPATH" && chmod -R 777 "$PROPATH"
WORKDIR $PROPATH

# Hint: the git dependency is already installed.

# Install gb.
RUN go get github.com/constabulary/gb/... && \
	go install github.com/constabulary/gb
