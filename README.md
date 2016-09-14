# Golang GB Docker Image

[GB is a project based build tool](http://getgb.io/) for the Go programming language.
This image provides a straightforward way to use GB projects with docker.
It makes use of the docker onbuild triggers.

## Supported tags
- `1.5`
- `1.5-onbuild`
- `1.5-alpine`
- `1.5-alpine-onbuild`
- `1.6`
- `1.6-onbuild`
- `1.6-alpine`
- `1.6-alpine-onbuild`
- `1.7`, `latest`
- `1.7-onbuild`, `onbuild`
- `1.7-alpine`, `alpine`
- `1.7-alpine-onbuild`, `alpine-onbuild`

## Usage
How to use this image Start a Go instance in your app.
The most straightforward way to use this image is to use a Go container as both the build and runtime environment. In your Dockerfile, writing something along the lines of the following will compile and run your project:

```
FROM desertbit/golang-gb:onbuild
```

Or for a minimal golang container:

```
FROM desertbit/golang-gb:alpine-onbuild
```

This image includes multiple ONBUILD triggers which should cover most applications. The build will copy the current project files into the project folder of the image ("*/project*") and build it with the gb tool.

This image also includes the CMD ["app"] instruction which is the default command when running the image without arguments.

You can then build and run the Docker image:

```
$ docker build -t my-golang-app .
$ docker run -it --rm --name my-running-app my-golang-app
```
