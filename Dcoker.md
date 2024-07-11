https://www.docker.com/blog/intro-guide-to-dockerfile-best-practices/

### attach shell to running container

```
docker exec -it <container-name> /bin/bash
```


### this needs to be broken down
```
docker run -d -p 80:8080 -p 50000:50000 --restart=on-failure -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock myjenkins
```
