FROM 192.168.1.105:5000/python:3.9-slim-bullseye
RUN apt-get update && apt install -y nginx curl supervisor pkg-config libmariadb-dev gcc
COPY default /etc/nginx/sites-enabled/default
WORKDIR /app
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY . .
RUN pip install -r requirment.text
#RUN curl -L -O https://artifacts.elastic.co/downloads/apm-server/apm-server-7.17.0-amd64.deb
#USER root
#RUN dpkg -i apm-server-7.17.0-amd64.deb
#RUN mv apm-server.yml /etc/apm-server/apm-server.yml
#UN chmod 755 /etc/apm-server/apm-server.yml
#RUN service apm-server start
CMD ["/usr/bin/supervisord"]
