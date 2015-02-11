ELK-Docker
==========

Docker configuration of Elasticsearch, Logstash and Kibana.

Build
=====

In order to build the image:

```
docker build -t elk:latest .
```

Run
===

In order to run the image:

```
docker run -d -p 5000:5601 --name elk -v /path/access-logs:/var/log/access elk
```

This will export to your local port 5000 kibana, so you will be able to access to kibana by:

```
http://localhost:5000
```

The ```/path/access-logs``` is the dir where the access logs are being added. This volume is mounted on the 
containter logstash processes the logs from it.

TODO
----

- [ ]  I think we don't need to install all this Java things on the image (just openjdk-7-jre-headless).
- [ ]  Push image to docker registry.
- [ ]  Split in three Docker images and use fig to set it up.
