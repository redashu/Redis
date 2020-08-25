# Redis 6.x installaion on rhel 7.5 

## update yum repo 

```
 yum update

```

## install epel 

```
 yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
```

## install remo repo

```
yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm

```

## install redis 

```
yum --enablerepo=remi install redis

```

## starting redis 

```
 systemctl enable --now  redis 

```
