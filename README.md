# Jenkins LTS with oc client ( oc-3.11.88-linux.tar.gz )

# How to build image?
```{r, engine='bash', count_lines}
$ docker build --tag=myuser/jenkins:lts /path/to/dockerfile
```

# How to push my image to private or public registry?
```{r, engine='bash', count_lines}
$ docker login -u user ip-or-domain-registry:port
$ docker push ip-or-domain-registry:port/myuser/jenkins:lts
```

# How to run container?
```{r, engine='bash', count_lines}
$ cd jenkins
$ docker run -d -p 49001:8080 -v /var/run/docker.sock:/var/run/docker.sock -v $PWD/jenkins:/var/jenkins_home:z -t gloriapg/jenkins:lts
```
