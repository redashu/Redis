# Redis configuration 

## change port and bind address 

### /etc/redis.conf 

port 6378
bind 0.0.0.0

### manage selinux 

```
semanage port -a  -t redis_port_t -p tcp 6378
```
### restart service

```
systemctl restart  redis
```

## connecting from  Remote client : 

```

root@3343ef5b067d:/data# redis-cli  -h 54.89.118.19 -p 6378
54.89.118.19:6378> 

```

## checking configuration from client side : 

```
54.89.118.19:6378> CONFIG GET port
1) "port"
2) "6378"
54.89.118.19:6378> CONFIG GET bind
1) "bind"
2) "0.0.0.0"

```


# Install HA node Cluster using cluster enable mode 

```
 19  redis-cli --cluster  create  172.31.57.249:6379 172.31.49.134:6379 172.31.61.239:6379 172.31.49.33:6379 172.31.57.146:6379 172.31.61.180:6379      --cluster-replicas 1
   20  redis-cli 
   21  redis-cli  cluster node 
   22  redis-cli -p 6379  cluster node 
   23  redis-cli -p 6379  cluster nodes 
   24  redis-cli -p 6379  cluster nodes   |   grep -i master
   25  redis-cli -p 6379  set x 100
   26  redis-cli 
   27  hostname -i
   28  redis-cli  -h 172.31.57.249  -p 6379  
   29  tail -f  /var/log/redis/redis.log 
   30  redis-cli  -h 172.31.57.249  -p 6379  
   31  redis-cli  -h
   32  history 
   33  redis-cli -p 6379  cluster
   34  hostname
   35  hostname -h
   36  hostname -i
   37  redis-cli  -h 172.31.57.249  -c 
   
   ```
   ## link 
   in docs
