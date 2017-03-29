# HDT-Docker
A Docker container to run the [HDT tools](https://github.com/rdfhdt/hdt-cpp).

All dependencies that are stated as optional for HDT are available in this container.
These dependencies include:
* Kyoto Cabinet
* Serd
* Raptor
* Libz

# Setup
```bash
$ docker pull rfdhdt/hdt-cpp
```

# Usage
The following HDT tools are available: rdf2hdt, hdt2rdf, hdtSearch

To discover how to use the tools, run them with the `-h` parameter:
```bash
docker run -it --rm rfdhdt/hdt-cpp rdf2hdt -h
```

For interacting with the tools, you will most likely have to mount one or more files or directies to the docker container,
the examples hereafter show how this can be done using the `-v` parameter for Docker `run`.

## RDF to HDT
Convert an RDF file to HDT:
```bash
$ docker run -it --rm -v "$(pwd)":/data rfdhdt/hdt-cpp rdf2hdt -f turtle /data/myfile.turtle /data/myfile.hdt
```

## HDT to RDF
```bash
$ docker run -it --rm -v "$(pwd)":/data rfdhdt/hdt-cpp hdt2rdf -f turtle /data/myfile.hdt /data/myfile.turtle
```

## HDT search
```bash
$ docker run -it --rm -v "$(pwd)":/data rfdhdt/hdt-cpp hdtSearch /data/myfile.hdt
```

