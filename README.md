To extend mariadb-103 image to include todo db:

$ git clone git@github.com:alpaslank-73/container.git

$ cd container/extend-image

$ sudo mkdir /temp

$ sudo s2i build . registry.redhat.io/rhel8/mariadb-103 yourtag --as-dockerfile /temp/Dockerfile -e MYSQL_ROOT_PASSWORD=redhat -e MYSQL_OPERATIONS_USER=opuser -e MYSQL_OPERATIONS_PASSWORD=oppass -e MYSQL_DATABASE=todo -e MYSQL_USER=alp -e MYSQL_PASSWORD=123456

$ cd /temp

Fix ownership in Dockerfile to avoid "permission denied" errors!

$ sudo vim Dockerfile
...
#RUN chown -R 1001:0 /tmp/src
RUN chown -R 27:0 /tmp/src
#USER 1001
USER 27
...

$ sudo podman build -t yuourtag .


To use an updated todo db (which includes deneme1 table) use container/extend-image-2 dir instead! 
