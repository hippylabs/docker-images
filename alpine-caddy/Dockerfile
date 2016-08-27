FROM alpine:3.4

RUN apk add --update --virtual dev curl && \
  curl "https://caddyserver.com/download/build?os=linux&arch=amd64&features=" \
  | tar --no-same-owner -C /usr/bin/ -xz caddy && \
  apk del dev && \
  rm -rf /var/cache/apk/*

COPY ./Caddyfile /Caddyfile

EXPOSE 80 443
VOLUME ['/data']

CMD ["caddy", "-conf", "/Caddyfile"]
