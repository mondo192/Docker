FROM golang:1.14.7-alpine3.12

ARG TOKEN=0
ENV TOKEN=$TOKEN

RUN apk --no-cache update && \
    apk --no-cache upgrade && \
    apk --no-cache add openssh curl git && \
    cat /dev/zero | ssh-keygen -t rsa -b 4096 -N "" && \
    eval "$(ssh-agent -s)" && \
    ssh-add ~/.ssh/id_rsa && \
    curl -s -X POST \
        -H "Authorization: token $TOKEN" \
        -H "Accept: application/vnd.github.v3+json" \
        https://api.github.com/user/keys \
        -d '{"title": "docker", "key": "'"$(cat ~/.ssh/id_rsa.pub)"'"}'
	
