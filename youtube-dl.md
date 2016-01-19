## Dockerfile
```
FROM alpine:3.2
ENV EDGE_REPOSITORY "http://dl-4.alpinelinux.org/alpine/edge/main/"
RUN apk update --repository $EDGE_REPOSITORY \
        && apk add py-pip ca-certificates \
        && apk add ffmpeg --repository $EDGE_REPOSITORY \
        && rm -rf /var/cache/apk/*

RUN pip install --upgrade youtube_dl

RUN export uid=1000 gid=1000 && \
    mkdir -p /home/developer && \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd && \
    echo "developer:x:${uid}:" >> /etc/group && \
    chown ${uid}:${gid} -R /home/developer

USER developer

WORKDIR /home/developer
ENTRYPOINT ["youtube-dl"]
CMD ["--help"]
```
## Build
```
docker build -t agusti/youtube-dl .
```

## Run
```
docker run -it --rm -v "$(pwd):/home/developer" agusti/youtube-dl "video_url"
```
