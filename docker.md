# Install on CentOS 7

```
sudo yum install -y docker
sudo systemctl enable docker
sudo systemctl start docker
```

## Basic command examples

### Search for CentOS images
```
docker search centos
```

### Image commands
```
docker pull docker.io/centos
docker images
```

### Container commands
```
docker run -it centos
```

```
docker ps
docker ps -a
```

```
docker exec -it laughing_mcnulty /bin/bash
```

```
docker stop laughing_mcnulty
```
