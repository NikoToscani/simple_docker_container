FROM ubuntu/nginx

WORKDIR /home

COPY ./nginx.conf /etc/nginx/

HEALTHCHECK --interval=5m --timeout=3s \
    CMD curl -f http://localhost/ || exit 1

ENTRYPOINT [ "/bin/bash", "-c", "nginx -g 'daemon off;'" ]