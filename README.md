# Redis backup and restore

## checking data store dir

```
[root@ip-172-31-57-123 ~]# redis-cli 
127.0.0.1:6379> auth Secure@xxx55
OK
127.0.0.1:6379> keys * 
1) "x"
2) "sudent"
127.0.0.1:6379> CONFIG GET dir
1) "dir"
2) "/var/lib/redis"

```

## to save backup 

```
Save 
```

## to start backup i background

```
BGsave

```

## bakcup using. Rdiff-backup

```
yum install rdiff-backup 

rdiff-backup  --preserve-numerical-ids  /var/lib/redis/ /root/redis

```
## setup cronjob with Rdiff-backup

```
@daily rdiff-backup --preserve-numerical-ids --no-file-statistics /var/lib/redis /root/redis

```
