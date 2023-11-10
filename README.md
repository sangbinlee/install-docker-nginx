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
