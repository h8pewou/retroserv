FROM nginx

# Install apache2-utils to get htpasswd command
RUN apt-get update -y && apt-get install -y apache2-utils && rm -rf /var/lib/apt/lists/*

# All environmental settings are overwritten by docker-compose

# Basic auth credentials
ENV BASIC_USERNAME=username
ENV BASIC_PASSWORD=fEw9KWUDekO33tAR

# Forward host and foward port as env variables
ENV FORWARD_HOST=wrp
ENV FORWARD_PORT=8080

# Nginx config file
WORKDIR /
COPY nginx-basic-auth.conf nginx-basic-auth.conf

# Startup script
COPY run.sh ./
RUN chmod 0755 ./run.sh
CMD [ "./run.sh" ]
