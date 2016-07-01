FROM alpine:3.4

RUN apk add --update python=2.7.12-r0 py-pip=8.1.2-r0 && \
  rm -rf /var/cache/apk/* && \
  #remove *.pyc *.pyo to reduce image size
  find /usr/lib -depth \
    \(   -type d -a -name test -o -name tests \) \
    -o \
    \( -type f -a -name '*.pyc' -o -name '*.pyo'  \) | xargs rm -rf

CMD ["python"]
