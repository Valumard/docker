1. build: 
```
docker build -t "YOUR_TAG_NAME" .
```
2. run:
```
docker run --name MyJenkins -p 9090:8080 -p 50000:50000 -v PATH_ON_YOUR_SYSTEM:/var/jenkins_home YOUR_TAG_NAME
```
-v is for volume binding. Needs read/write permissions