# Easy DockerFile

## nginx with curl

### Build image 
```
docker build . -t johnzheng/nginx -f Dockerfile_nginxcurl 
docker push johnzheng/nginx
```

### Use command
```
k run nginx --image=johnzheng/nginx
k exec -ti nginx-7dd77d88cc-24fdj -- curl www.baidu.com
```


## alpine with curl

### Build image 
```
docker build . -t johnzheng/alpine -f Dockerfile_alpinecurl 
docker push johnzheng/alpine
```

### Use command
```
k run -ti --rm --restart=Never --image=johnzheng/alpine -- curl www.baidu.com
```


## ubuntu with kubectl

### Build image 
```
docker build . -t johnzheng/ubuntukubectl -f Dockerfile_ubuntuWithKubectl
docker push johnzheng/ubuntukubectl
```

### Use command
```
ubuntu@ip-172-31-17-153:~$ docker run -v /home/ubuntu/.kube:/root/.kube -ti johnzheng/ubuntukubectl
Unable to find image 'johnzheng/ubuntukubectl:latest' locally
latest: Pulling from johnzheng/ubuntukubectl
16c48d79e9cc: Pull complete 
... ...
Digest: sha256:d7725a7cc6b4dbdcd8e1f2ddc79922a62ebd11d06aecbc12ffa0e208cbd3473d
Status: Downloaded newer image for johnzheng/ubuntukubectl:latest

root@bfa762a22742:/# kubectl get nodes
NAME                           AGE
ip-10-250-5-191.ec2.internal   486d
ip-10-250-7-20.ec2.internal    35d

```
