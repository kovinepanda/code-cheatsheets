# Docker cli commands

```bash
#Stop all 
docker stop $(docker ps -a -q)

#Remove all 
docker rm $(docker ps -a -q)
```

## Copy docker images from host to another without using a repistory
```bash
# Host
docker save -o <path for generated tar file> <image name>

# Client
docker load -i ~/Downloads/myfile.tar <image name>
```
> Source https://stackoverflow.com/a/23938978
