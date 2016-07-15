dvara Docker image
==================
This is the Docker image for the dvara MongoDB connection pooling proxy.

For more info and help with dvara, go to https://github.com/facebookgo/dvara.

Usage
=====
In general:
```
$ docker run [docker run options] pataquets/dvara [dvara options]
```
Common Docker options when running are:

- Exposing ports (```-p```). Mappings must match with dvara options for it to be reachable.
- Container linking (```--link```), if the target MongoDB instance runs in another container.

If no options for dvara are provided, it will default to```--help``` to show usage info.

Examples
--------

Launch as a background container detached from console, exposing dvara's default ports:
```
$ docker run -d -p 6000-6010:6000-6010 pataquets/dvara -addrs mongo.example.com:27017 
```

For debugging, replace ```-d``` by ```-it``` to launch a container attached to the console. You can also enable dvara's logging.
```
$ docker run -it -p 6000-6010:6000-6010 pataquets/dvara -addrs mongo.example.com:27017 -dvara.proxy-all
```
