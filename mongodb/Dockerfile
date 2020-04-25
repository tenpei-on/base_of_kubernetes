FROM alpine:3.9

COPY docker-entrypoint.sh /usr/local/bin

RUN \
adduser -g mongodb -DH -u 1000 mongodb; \
# apk is package install command 
apk --no-cache add mongodb=4.0.5-r0; \
chmod +x /usr/local/bin/docker-entrypoint.sh; \
mkdir -p /data/db; \
chown -R mongodb:mongodb /data/db;

# VOLUME and EXPOSE are commands Docker image uses (EXPOSE: listening port)
VOLUME /data/db

# mongodb default port
EXPOSE 27017

ENTRYPOINT [ "docker-entrypoint.sh" ]
CMD [ "mongod" ]
