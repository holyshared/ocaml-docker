# ocaml-docker

## Environments

* User in container - **develop**
* Workking directory - **/home/develop/project**
* OCaml compiler **4.09.0**
* OPAM **2.x.x**

## Basis usage

1. Create build script

	Create a script for build.

	```shell
	#!/usr/bin/env bash

	eval `opam config env`

	opam install -y cohttp
	```

2. Execute build script on docker container

	Specify the -v option, mount the directory on the host side, and execute the script.

	```shell
	docker run -v `pwd`:/home/develop/project holyshared/ocaml:latest ./[build script]
	```
