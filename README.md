Hello Server [![Build Status](https://travis-ci.org/breerly/hello-server.svg?branch=master)](https://travis-ci.org/breerly/hello-server)
============

A Programmable, 6mb, Hello World Docker Appliance.


Run with default settings:

```
$ docker run -d -p 8080:8080 breerly/hello-server

2016/01/30 10:16:40 Listening on :8080

$ curl `docker-machine ip default`:8080

Hello World!
```

Customize with environmental variables:

```
$ docker run -d -p 8080:8080 \
    -e HELLO_MESSAGE="Hello Johnson!" \
    -e HELLO_PORT=8080 \
    -e HELLO_SLEEP=1 \
    -e HELLO_STATUS_CODE=404 \
    breerly/hello-server

2016/01/30 10:16:39 Sleeping for 1 seconds...
2016/01/30 10:16:40 Listening on :8080

$ curl `docker-machine ip default`:8081

Hello World!
```

Run from Docker Compose:

```
hello:
    image: breerly/hello-server
    ports:
        - 8082:8082
    environment:
        - HELLO_PORT=8080
        - HELLO_MESSAGE=hello!
        - HELLO_SLEEP=1
        - HELLO_STATUS_CODE=404
```

Cheers!
