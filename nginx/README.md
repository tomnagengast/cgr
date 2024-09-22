# Nginx

Docs from https://images.chainguard.dev/directory/image/nginx/overview

We have two image variants available:

- A minimal runtime variant that removes shells and package managers for additional security.
- An nginx:latest-dev variant that contains the `apk` package manager and the `bash`, `ash`, and `sh` shells.

## Usage

```
docker run --rm -p 8080:8080 \
    -v $(pwd)/html:/usr/share/nginx/html \
    cgr.dev/chainguard/nginx:latest
```

## Adding a Custom Server Block

```
docker run --rm -p 4000:4000 \
    -v $(pwd)/html:/www/data \
    -v $(pwd)/conf.d:/etc/nginx/conf.d \
    cgr.dev/chainguard/nginx:latest
```


## Replacing the Default nginx Configuration

```
docker run --rm -p 4000:4000 \
    -v $(pwd)/html:/www/data \
    -v $(pwd)/nginx-conf:/etc/nginx \
    cgr.dev/chainguard/nginx:latest
```
