Dockerfile - Dockerfile_app1
docker build -t myflaskapp1 .
docker run -d --name flaskapp1-cont -p 5001:5000 myflaskapp1

Dockerfile - Dockerfile_app2
docker build -t myflaskapp2 .
docker run -d --name flaskapp2-cont -p 5002:5000 myflaskapp2

Dockerfile - Dockerfile
docker build -t mynginxapp .
docker run -d -p 80:80 --name mynginxapp-container mynginxapp

http://<hostip>/app1
http://<hostip>/app2