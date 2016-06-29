FROM alpine:3.4

RUN apk add --update nginx=1.10.1-r1 && \
  #directory for pid and lock file
  mkdir -p /run/nginx && \
  rm -rf /var/cache/apk/* && \
  #direct logs to stdout/stderr
  ln -sf /dev/stdout /var/log/nginx/access.log && \
  ln -sf /dev/stderr /var/log/nginx/error.log

ADD nginx.conf /etc/nginx/nginx.conf
ADD conf.d /etc/nginx/conf.d

EXPOSE 80 443

ENTRYPOINT ["nginx", "-g", "daemon off;"]
