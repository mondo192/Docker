FROM golang:1.14.7-alpine3.12

ARG TOKEN=0
ENV TOKEN=$TOKEN

RUN apk --no-cache update && \
    apk --no-cache upgrade && \
	apk --no-cache add openssh && \
	cat /dev/zero | ssh-keygen -t rsa -b 4096 -N "" && \
	eval "$(ssh-agent -s)" && \
	ssh-add ~/.ssh/id_rsa && \
	echo $TOKEN
