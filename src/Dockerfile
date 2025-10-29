FROM nginx:latest

WORKDIR /home

COPY ./server/hello.c /home
COPY ./nginx/nginx.conf /etc/nginx/

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y gcc libfcgi-dev spawn-fcgi; \
    gcc hello.c -lfcgi

ENTRYPOINT [ "/bin/bash", "-c", "nginx -g 'daemon off;' | spawn-fcgi -p 8080 a.out" ]