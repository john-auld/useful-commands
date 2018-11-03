# Install NGINX on CentOS 7 from the offical repo

Set up the yum repository for RHEL or CentOS by creating the file nginx.repo in /etc/yum.repos.d, for example using vi:
```
sudo vi /etc/yum.repos.d/nginx.repo
```

Add the following lines to nginx.repo:
```
[nginx]
name=nginx repo
baseurl=https://nginx.org/packages/mainline/centos/7/$basearch/
gpgcheck=0
enabled=1
```

```
sudo yum update
sudo yum install nginx
```
