# Python

Docs from https://images.chainguard.dev/directory/image/python/overview

We have two image variants available:

- A python:latest-dev variant that contains the pip and apk package managers and the bash, ash, and sh shells.
- A minimal runtime variant that removes shells and package managers for additional security.

## Usage

```
docker build . -t fastapi && docker run --rm fastapi
```
