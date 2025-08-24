# ps-dz4.11
PurpleSchool DZ 4.11

```
vg @ubu24srv: ~/purpleschool/ps-dz4.11 git(dz)  
$ ls  
default.conf  Dockerfile  index.html  README.md


$ cat index.html    
<h1>Purplescool</h1>  
<p>ДЗ 4.11</p>


$ cat Dockerfile    
FROM nginx:alpine  
COPY ./index.html /usr/share/nginx/html/index.html  
COPY ./default.conf /etc/nginx/conf.d/default.conf


$ d build . -t mynginx  
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.  
           Install the buildx component to build images with BuildKit:  
           https://docs.docker.com/go/buildx/  
  
Sending build context to Docker daemon  79.36kB  
Step 1/3 : FROM nginx:alpine  
---> 4a86014ec699  
Step 2/3 : COPY ./index.html /usr/share/nginx/html/index.html  
---> Using cache  
---> 7ca79d81600b  
Step 3/3 : COPY ./default.conf /etc/nginx/conf.d/default.conf  
---> Using cache  
---> ef5861652c6f  
Successfully built ef5861652c6f  
Successfully tagged mynginx:latest


$ d run -d mynginx  
507255c83058c1111767c64f9793e111176fa45d6f2b5c16aaa3b5921b2eb7c8


$ d exec -it 507255c83058 sh  
/ # curl localhost:80  
<h1>Purplescool</h1>  
<p>ДЗ 4.11</p>  
/ #
```

