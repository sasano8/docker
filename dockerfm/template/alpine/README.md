# How to build

``` bash
# create image from Dockerfile in current directory.
docker build -t <username>/imagename .

# run as background(-d) and bind port(-p publish:dest to port forward)
docker run -p 8080:80 -d <username>/imagename

```

