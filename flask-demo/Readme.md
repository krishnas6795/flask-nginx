# NGINX - Flask Demo

This demo application contains two flask application running in two different containers and the application is served via NGINX server.

Dockerfile - Dockerfile_app1
```bash
docker build -t myflaskapp1 .
docker run -d --name flaskapp1-cont -p 5001:5000 myflaskapp1
```
```bash
docker stop flaskapp1-cont
docker rm flaskapp1-cont
docker rmi myflaskapp1
```
Dockerfile - Dockerfile_app2
```bash
docker build -t myflaskapp2 .
docker run -d --name flaskapp2-cont -p 5002:5000 myflaskapp2
```
```bash
docker stop flaskapp2-cont
docker rm flaskapp2-cont
docker rmi myflaskapp2
```

Dockerfile - Dockerfile_nginx_working
```bash
docker build -t mynginxapp .
docker run -d -p 80:80 --name mynginxapp-container mynginxapp
```

```bash
docker stop mynginxapp-container
docker rm mynginxapp-container
docker rmi mynginxapp
```

**URL**
* `http://<host_ip or domain_name>/app1`
* `http://<host_ip or domain_name>/app2`

**To get the IP address**
```bash
curl ifconfig.me
```

**Setting environment variable**
```bash
vi .bashrc
export ext_ip=`curl ifconfig.me`
```

```bash
echo ${ext_ip}
output: your extenal ip
```


