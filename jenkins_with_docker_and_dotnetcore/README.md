1. build: 
```
docker build -t "YOUR_TAG_NAME" .
```
2. run:
```
docker run --name MyJenkins -p 8080:8080 -p 50000:50000 -v PATH_ON_YOUR_SYSTEM:/var/jenkins_home YOUR_TAG_NAME
```

-v is for volume binding. Needs read/write permissions  
-p the ports are up to you  

3. have fun with Jenkins!

Open up a browser, go to localhost:8080 (or whatever port you've chosen) and you have your running CI/CD system.
