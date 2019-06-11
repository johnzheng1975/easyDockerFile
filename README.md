# Easy DockerFile

## nginx with curl

### Build image 
docker build . -t johnzheng/nginx -f Dockerfile_nginxcurl 
docker push johnzheng/nginx

### Use command
k run nginx --image=johnzheng/nginx
k exec -ti nginx-7dd77d88cc-24fdj -- curl www.baidu.com


## alpine with curl

### Build image 
docker build . -t johnzheng/alpine -f Dockerfile_alpinecurl 
docker push johnzheng/alpine

### Use command
k run -ti --rm --restart=Never --image=johnzheng/alpine -- curl www.baidu.com
