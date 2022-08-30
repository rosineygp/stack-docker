# Stack Docker

Create Dockerfile, build and push using [Stackspot](https://stackspot.com/) technologies.

## How to use

```shell
# import stack

stk import stack https://github.com/rosineygp/stack-docker
```

After import the stack you can use the following commands

```shell
# create your app

$ stk create app docker-stuffs --stackfile stack-docker/default 
- Application docker-stuffs successfully created!
```

Now is possible create you custom `Dockerfile` at docker-stuffs folder.

```shell
# create new dockerfile

stk apply plugin create-dockerfile 

# after run this command the following questions will be asked.

? Docker Base Image  (alpine) python
? Docker Image Tag  (latest) 3.7
? Install System Packages Yes
? Package Manager apt-get
? Package Names (separated by spaces)  (curl) wget
? Install Code Packages Yes
? Code Package Manager pip
? Code Package Names (separated by spaces)  (pyyaml)
- Plugin stack-docker/create-dockerfile applied.
```

A new folder is generated and its name contains name, version and sorted packages added. `(eg. python-3-7-wget-pip-pyyaml)`.

And inside the folder will be generated the `Dockerfile`.

```Dockerfile
# Dockefile

FROM python:3.7

RUN apt-get update && apt-get install -y wget
RUN pip install pyyaml
```

## Build

For build all `Dockerfiles` previously generated, just run:

```shell
# Build all Dockerfiles

stk run stack-docker/docker-build
```