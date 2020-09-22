FROM alpine:3.12

RUN apk add --no-cache --update nginx \
    && apk add --no-cache --update nodejs npm \
    && npm install -g nodemon \
    && chown -R nginx:www-data /var/lib/nginx 

ADD https://github.com/just-containers/s6-overlay/releases/download/v1.21.8.0/s6-overlay-amd64.tar.gz /tmp/
RUN gunzip -c /tmp/s6-overlay-amd64.tar.gz | tar -xf - -C /

ENTRYPOINT ["/init"]

ADD root /

WORKDIR /app

EXPOSE 80 443