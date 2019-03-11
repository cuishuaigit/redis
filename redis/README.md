#Redis

this is a redis  statesulset yaml

## Usage
build yourself  config image
```bash
docker build -t fastop/busybox:redisconf .
```

modify the tag as your registry,my registry is fastop.

if you build yourself config imag,you must modify  redis-statefulset.yaml with the right config image,default it is fastop/busybox:redisconf.
```bash
kubectl create -f redis-statefulset.yaml 
```

## Redis Config
redis use a password and Disable dangerous command.
```    
    requirepass MV523SXtKZwAi58
    rename-command FLUSHALL ""
    rename-command FLUSHDB "MV523SXtKZwAi58"
    rename-command CONFIG "rcconfig"
```
