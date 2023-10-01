# install-docker-nginx
install-docker-nginx


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
# 
# 
# 
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
