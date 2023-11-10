# install-docker-nginx
install-docker-nginx


#  docker-compose up -d --build


    
    sangbinlee9@master:~/fastapi-vue$ docker-compose up -d --build
    Command 'docker-compose' not found, but can be installed with:
    sudo snap install docker          # version 20.10.24, or
    sudo apt  install docker-compose  # version 1.29.2-1
    See 'snap info docker' for additional versions.
    sangbinlee9@master:~/fastapi-vue$ docker compose up -d --build
    permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json?all=1&filters=%7B%22label%22%3A%7B%22com.docker.compose.config-hash%22%3Atrue%2C%22com.docker.compose.project%3Dfastapi-vue%22%3Atrue%7D%7D": dial unix /var/run/docker.sock: connect: permission denied
    

    
    sangbinlee9@master:~/fastapi-vue$ ls -al /var/run/docker.sock
    srw-rw---- 1 root docker 0 Nov 10 19:23 /var/run/docker.sock





# sudo chmod 666 /var/run/docker.sock

    
    sangbinlee9@master:~/fastapi-vue$ ls -al /var/run/docker.sock
    srw-rw---- 1 root docker 0 Nov 10 19:23 /var/run/docker.sock
    sangbinlee9@master:~/fastapi-vue$  sudo chmod 666 /var/run/docker.sock
    [sudo] password for sangbinlee9:
    sangbinlee9@master:~/fastapi-vue$ ls -al /var/run/docker.sock
    srw-rw-rw- 1 root docker 0 Nov 10 19:23 /var/run/docker.sock




#  docker compose up -d --build


    
    
    sangbinlee9@master:~/fastapi-vue$ docker-compose up -d --build
    Command 'docker-compose' not found, but can be installed with:
    sudo snap install docker          # version 20.10.24, or
    sudo apt  install docker-compose  # version 1.29.2-1
    See 'snap info docker' for additional versions.
    sangbinlee9@master:~/fastapi-vue$ docker compose up -d --build
    [+] Building 52.6s (12/12) FINISHED                              docker:default
     => [backend internal] load build definition from Dockerfile               0.1s
     => => transferring dockerfile: 249B                                       0.0s
     => [backend internal] load .dockerignore                                  0.1s
     => => transferring context: 2B                                            0.0s
     => [backend internal] load metadata for docker.io/library/python:3.11-bu  2.6s
     => [backend 1/7] FROM docker.io/library/python:3.11-buster@sha256:3a19b  38.1s
     => => resolve docker.io/library/python:3.11-buster@sha256:3a19b4d6ce4402  1.2s
     => => sha256:3a19b4d6ce4402d11bb19aa11416e4a262a60a57707a5cd 988B / 988B  0.0s
     => => sha256:35a9527e56796de39e7132531a63f13c97e77ea1ca1 2.01kB / 2.01kB  0.0s
     => => sha256:5bf9a636079f0257fa52c3bbed42ec29d3b975cfd1e 7.52kB / 7.52kB  0.0s
     => => sha256:b1e7e053c9f6f57c6d95002167a6d57aed6aacf0 51.87MB / 51.87MB  18.1s
     => => sha256:ac8bb7e1a32398e26c129ce64e2ddc3e7ec6c34d 50.45MB / 50.45MB  18.3s
     => => sha256:3b1c264c0ad4598c25048a6dbd3030086cc5c7400 17.58MB / 17.58MB  5.2s
     => => sha256:a2e1e233599c00054fb839db78b4d42e6f12f3 191.88MB / 191.88MB  30.3s
     => => extracting sha256:ac8bb7e1a32398e26c129ce64e2ddc3e7ec6c34d93424b24  1.7s
     => => sha256:0ebfe287e9761b9b7dd1703470ff3473a62fe75238 6.15MB / 6.15MB  20.9s
     => => sha256:de5c87c207fdbeb45bd9af3dfcedfa01ca8dabc9 22.31MB / 22.31MB  24.2s
     => => extracting sha256:3b1c264c0ad4598c25048a6dbd3030086cc5c74000e11d04  0.4s
     => => extracting sha256:b1e7e053c9f6f57c6d95002167a6d57aed6aacf04dd2f8e6  1.8s
     => => sha256:7d34d7fb27b1dc3c88ed00968ed95052da3afce13640f4 244B / 244B  21.1s
     => => sha256:342382b8cc09c8dcb9c3afb12c6c6ceb2f32eec26b 3.09MB / 3.09MB  22.9s
     => => extracting sha256:a2e1e233599c00054fb839db78b4d42e6f12f36b64280aa6  5.0s
     => => extracting sha256:0ebfe287e9761b9b7dd1703470ff3473a62fe75238f3de01  0.2s
     => => extracting sha256:de5c87c207fdbeb45bd9af3dfcedfa01ca8dabc9849ded7a  0.5s
     => => extracting sha256:7d34d7fb27b1dc3c88ed00968ed95052da3afce13640f4b1  0.0s
     => => extracting sha256:342382b8cc09c8dcb9c3afb12c6c6ceb2f32eec26b508322  0.2s
     => [backend internal] load build context                                  0.0s
     => => transferring context: 239B                                          0.0s
     => [backend 2/7] RUN mkdir app                                            3.6s
     => [backend 3/7] WORKDIR /app                                             0.1s
     => [backend 4/7] COPY requirements.txt .                                  0.1s
     => [backend 5/7] RUN pip install --upgrade pip                            4.2s
     => [backend 6/7] RUN pip install -r requirements.txt                      3.4s
     => [backend 7/7] COPY src/ .                                              0.1s
     => [backend] exporting to image                                           0.3s
     => => exporting layers                                                    0.3s
     => => writing image sha256:1f0e427b6ea3fa454b29b8d8cd93ba3cd5af6ca99d254  0.0s
     => => naming to docker.io/library/fastapi-vue-backend                     0.0s
    [+] Running 2/2
     ✔ Network fastapi-vue_default      Creat...                               0.1s
     ✔ Container fastapi-vue-backend-1  S...                                   0.0s
    sangbinlee9@master:~/fastapi-vue$







# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# ./gradlew clean build


![image](https://github.com/sangbinlee/install-docker-nginx/assets/4024414/384490b2-8715-4e75-9db5-451795ab5669)















# 



    
    root@kpismain:~/tomcat-mssql# ll
    total 128996
    drwxr-xr-x  2 root root      4096 Sep 30 17:22 ./
    drwx------ 16 root root      4096 Oct  1 00:45 ../
    -rw-r--r--  1 root root       594 Sep 23 13:22 docker-compose.yml
    -rw-r--r--  1 root root 132066730 Sep 28 16:15 ROOT.war
    -rw-r--r--  1 root root      7847 Sep 23 13:16 server.xml
    








# 
    root@kpismain:~/tomcat-mssql# cat docker-compose.yml
    # docker compose up -d
    # docker compose down
    version: '3.4'
    
    services:
      tomcat-85-mssql:
        container_name: "tomcat-85-mssql"
        image: tomcat:85
        environment: # 환경 변수 값
          - system.mode=dev
          - log.location=/usr/local/tomcat/logs/part-zone/mssql
          - TZ=Asia/Seoul
        volumes: # 볼륨 마운트
          - /resources:/resources
          - /productImage:/productImage
          - /userinfo:/userinfo
          - /root/tomcat-mssql/ROOT.war:/usr/local/tomcat/webapps/ROOT.war
          - /root/tomcat-mssql/server.xml:/usr/local/tomcat/conf/server.xml
        ports:
          - "9090:9090"




    
          
    root@kpismain:~/tomcat-mssql# cat server.xml
    
    
            <Context docBase="/resources" path="/resources" reloadable="true" />
          <Context docBase="/productImage" path="/productImage" reloadable="true"/>
          <Context docBase="/userinfo" path="/userinfo" reloadable="true"/>
            <Context sessionCookieName="mssql_JSESSIONID" path="/" reloadable="true" />
          </Host>
        </Engine>
      </Service>
    </Server>
