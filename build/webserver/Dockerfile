FROM nginx

RUN rm /etc/nginx/conf.d/default.conf

COPY ./conf/app.template-nossl /tmp/

COPY ./conf/app.template-ssl /tmp/

COPY ./script/genAppNginx /usr/local/bin/

RUN apt-get update && \
    apt-get install openssl -y

RUN openssl dhparam -out /etc/nginx/dhparam.pem 2048
