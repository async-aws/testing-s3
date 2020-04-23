# Testing S3

A Dockerfile for [jubos/fake-s3](https://github.com/jubos/fake-s3)
to test request to S3 locally.

This project is a fork of [lphoward/fake-s3](https://github.com/lphoward/fake-s3).

## Usage

```cli
docker run -rm -p 4569:4569 -d asyncaws/testing-s3
```

If you want the container to use a volume, then

```cli
docker run --name my_s3 -v /fakes3_root -d asyncaws/testing-s3
```

The fake-s3 root directory will then be added as a volume on the Docker host. To get the volume

```cli
docker inspect --format "{{range .Mounts}}{{.Source}}{{end}}" my_s3
```
