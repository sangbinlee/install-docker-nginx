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







# sangbinlee9@master:~/fastapi-vue/services/backend/src$ vi main.py

![image](https://github.com/sangbinlee/install-docker-nginx/assets/4024414/c718ac60-868e-4cb8-8c9f-fa782c51d22b)








# http://192.168.0.65:5000/

![image](https://github.com/sangbinlee/install-docker-nginx/assets/4024414/c4b731c9-5d48-4376-9513-be8747c36eb3)

![image](https://github.com/sangbinlee/install-docker-nginx/assets/4024414/4e183c0f-3d77-4ce2-84c7-0a0374cf35b5)



# sudo apt install npm
# npm install -g @vue/cli
# 
# 
#  sudo apt install nodejs
# nodejs --version
#  sudo apt install npm
# npm --version
# npm install vue@next
# sudo npm install -g @vue/cli
#  vue -V
#  vue create frontend

    
    
    
    
    sangbinlee9@master:~/fastapi-vue/services$ ll
    total 16
    drwxrwxr-x 4 sangbinlee9 sangbinlee9 4096 Nov 10 20:24 ./
    drwxrwxr-x 4 sangbinlee9 sangbinlee9 4096 Nov 10 20:19 ../
    drwxrwxr-x 3 sangbinlee9 sangbinlee9 4096 Nov 10 19:51 backend/
    drwxrwxr-x 6 sangbinlee9 sangbinlee9 4096 Nov 10 20:25 frontend/
    sangbinlee9@master:~/fastapi-vue/services$

    
    sangbinlee9@master:~/fastapi-vue/services$ cd frontend/
    sangbinlee9@master:~/fastapi-vue/services/frontend$ ll
    total 856
    drwxrwxr-x   6 sangbinlee9 sangbinlee9   4096 Nov 10 20:25 ./
    drwxrwxr-x   4 sangbinlee9 sangbinlee9   4096 Nov 10 20:24 ../
    -rw-rw-r--   1 sangbinlee9 sangbinlee9     73 Nov 10 20:25 babel.config.js
    drwxrwxr-x   7 sangbinlee9 sangbinlee9   4096 Nov 10 20:25 .git/
    -rw-rw-r--   1 sangbinlee9 sangbinlee9    231 Nov 10 20:25 .gitignore
    -rw-rw-r--   1 sangbinlee9 sangbinlee9    279 Nov 10 20:25 jsconfig.json
    drwxrwxr-x 574 sangbinlee9 sangbinlee9  20480 Nov 10 20:25 node_modules/
    -rw-rw-r--   1 sangbinlee9 sangbinlee9    884 Nov 10 20:25 package.json
    -rw-rw-r--   1 sangbinlee9 sangbinlee9 808475 Nov 10 20:25 package-lock.json
    drwxrwxr-x   2 sangbinlee9 sangbinlee9   4096 Nov 10 20:25 public/
    -rw-rw-r--   1 sangbinlee9 sangbinlee9    320 Nov 10 20:25 README.md
    drwxrwxr-x   4 sangbinlee9 sangbinlee9   4096 Nov 10 20:25 src/
    -rw-rw-r--   1 sangbinlee9 sangbinlee9    118 Nov 10 20:25 vue.config.js
    sangbinlee9@master:~/fastapi-vue/services/frontend$








# 
#  vue add router




    
    sangbinlee9@master:~/fastapi-vue/services/frontend$  vue add router
     WARN  There are uncommitted changes in the current repository, it's recommended to commit or stash them first.
    ? Still proceed? Yes
    
    📦  Installing @vue/cli-plugin-router...
    
    
    up to date, audited 973 packages in 4s
    
    109 packages are looking for funding
      run `npm fund` for details
    
    4 moderate severity vulnerabilities
    
    To address all issues (including breaking changes), run:
      npm audit fix --force
    
    Run `npm audit` for details.
    ✔  Successfully installed plugin: @vue/cli-plugin-router
    
    ? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
    
    🚀  Invoking generator for @vue/cli-plugin-router...
    📦  Installing additional dependencies...
    
    
    added 2 packages, and audited 975 packages in 5s
    
    110 packages are looking for funding
      run `npm fund` for details
    
    4 moderate severity vulnerabilities
    
    To address all issues (including breaking changes), run:
      npm audit fix --force
    
    Run `npm audit` for details.
    ⚓  Running completion hooks...
    
    ✔  Successfully invoked generator for plugin: @vue/cli-plugin-router
    sangbinlee9@master:~/fastapi-vue/services/frontend$













# npm install --save axios@1.2.1 vuex@4.1.0 bootstrap@5.2.3

    
    sangbinlee9@master:~/fastapi-vue/services/frontend$
    sangbinlee9@master:~/fastapi-vue/services/frontend$ npm install --save axios@1.2.1 vuex@4.1.0 bootstrap@5.2.3
    
    added 9 packages, and audited 984 packages in 7s
    
    112 packages are looking for funding
      run `npm fund` for details
    
    5 moderate severity vulnerabilities
    
    To address issues that do not require attention, run:
      npm audit fix
    
    To address all issues (including breaking changes), run:
      npm audit fix --force
    
    Run `npm audit` for details.
    sangbinlee9@master:~/fastapi-vue/services/frontend$
    





# npm run serve


    
    
    sangbinlee9@master:~/fastapi-vue/services/frontend$ npm run serve
    
    > frontend@0.1.0 serve
    > vue-cli-service serve
    
     INFO  Starting development server...
     ERROR  Error: @vitejs/plugin-vue requires vue (>=3.2.13) or @vue/compiler-sfc to be present in the dependency tree.
    Error: @vitejs/plugin-vue requires vue (>=3.2.13) or @vue/compiler-sfc to be present in the dependency tree.
        at Object.<anonymous> (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/vue-loader/dist/compiler.js:14:15)
        at Module._compile (internal/modules/cjs/loader.js:999:30)
        at Object.Module._extensions..js (internal/modules/cjs/loader.js:1027:10)
        at Module.load (internal/modules/cjs/loader.js:863:32)
        at Function.Module._load (internal/modules/cjs/loader.js:708:14)
        at Module.require (internal/modules/cjs/loader.js:887:19)
        at require (internal/modules/cjs/helpers.js:74:18)
        at Object.<anonymous> (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/vue-loader/dist/index.js:29:20)
        at Module._compile (internal/modules/cjs/loader.js:999:30)
        at Object.Module._extensions..js (internal/modules/cjs/loader.js:1027:10)
        at Module.load (internal/modules/cjs/loader.js:863:32)
        at Function.Module._load (internal/modules/cjs/loader.js:708:14)
        at Module.require (internal/modules/cjs/loader.js:887:19)
        at require (internal/modules/cjs/helpers.js:74:18)
        at /home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/config/base.js:154:16
        at /home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/Service.js:268:40
        at Array.forEach (<anonymous>)
        at Service.resolveChainableWebpackConfig (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/Service.js:268:26)
        at Service.resolveWebpackConfig (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/Service.js:272:48)
        at PluginAPI.resolveWebpackConfig (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/PluginAPI.js:132:25)
        at serve (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/commands/serve.js:79:31)
        at Service.run (/home/sangbinlee9/fastapi-vue/services/frontend/node_modules/@vue/cli-service/lib/Service.js:262:12)
        at processTicksAndRejections (internal/process/task_queues.js:97:5)
    sangbinlee9@master:~/fastapi-vue/services/frontend$






# npm i vue@3.2.26


#  npm run serve
    sangbinlee9@master:~/fastapi-vue/services/frontend$ npm run serve
    
    > frontend@0.1.0 serve
    > vue-cli-service serve
    
     INFO  Starting development server...
    
    
     DONE  Compiled successfully in 5444ms                                                                                9:30:25 PM
    
    
      App running at:
      - Local:   http://localhost:8081/
      - Network: http://192.168.0.65:8081/
    
      Note that the development build is not optimized.
      To create a production build, run npm run build.



![image](https://github.com/sangbinlee/install-docker-nginx/assets/4024414/1ac7b5b2-12fb-4ef2-bfa8-5c591895fd93)




#  vi docker-compose.yml
    sangbinlee9@master:~/fastapi-vue$ vi docker-compose.yml

    
    version: '3.8'
    
    services:
    
      backend:
        build: ./services/backend
        ports:
          - 5000:5000
        volumes:
          - ./services/backend:/app
        command: uvicorn src.main:app --reload --host 0.0.0.0 --port 5000
    
      frontend:
        build: ./services/frontend
        volumes:
          - './services/frontend:/app'
          - '/app/node_modules'
        ports:
          - 8081:8081




#  docker compose up -d --build

    sangbinlee9@master:~/fastapi-vue$ docker compose up -d --build




    
    /
    sangbinlee9@master:~/fastapi-vue$ vi docker-compose.yml
    sangbinlee9@master:~/fastapi-vue$ docker compose up -d --build
    [+] Building 84.5s (23/23) FINISHED                                                                              docker:default
     => [backend internal] load build definition from Dockerfile                                                               0.0s
     => => transferring dockerfile: 249B                                                                                       0.0s
     => [backend internal] load .dockerignore                                                                                  0.0s
     => => transferring context: 2B                                                                                            0.0s
     => [frontend internal] load build definition from Dockerfile                                                              0.1s
     => => transferring dockerfile: 239B                                                                                       0.0s
     => [frontend internal] load .dockerignore                                                                                 0.1s
     => => transferring context: 2B                                                                                            0.0s
     => [backend internal] load metadata for docker.io/library/python:3.11-buster                                              1.6s
     => [frontend internal] load metadata for docker.io/library/node:lts-alpine                                                2.5s
     => [backend internal] load build context                                                                                  0.0s
     => => transferring context: 182B                                                                                          0.0s
     => [backend 1/7] FROM docker.io/library/python:3.11-buster@sha256:3a19b4d6ce4402d11bb19aa11416e4a262a60a57707a5cda5787a8  0.0s
     => CACHED [backend 2/7] RUN mkdir app                                                                                     0.0s
     => CACHED [backend 3/7] WORKDIR /app                                                                                      0.0s
     => CACHED [backend 4/7] COPY requirements.txt .                                                                           0.0s
     => CACHED [backend 5/7] RUN pip install --upgrade pip                                                                     0.0s
     => CACHED [backend 6/7] RUN pip install -r requirements.txt                                                               0.0s
     => CACHED [backend 7/7] COPY src/ .                                                                                       0.0s
     => [backend] exporting to image                                                                                           0.0s
     => => exporting layers                                                                                                    0.0s
     => => writing image sha256:f05696284097a9bb6254a76ebc99d36187d596d0d3b70f8c0a8afaec80b145d7                               0.0s
     => => naming to docker.io/library/fastapi-vue-backend                                                                     0.0s
     => [frontend 1/6] FROM docker.io/library/node:lts-alpine@sha256:8e015de364a2eb2ed7c52a558e9f716dcb615560ffd132234087c10c  7.1s
     => => resolve docker.io/library/node:lts-alpine@sha256:8e015de364a2eb2ed7c52a558e9f716dcb615560ffd132234087c10ccc1f2c63   0.0s
     => => sha256:3a617f439a70c99c88b4f6179a9c23bdc9ab21df2ad7354aae079c52caa5e3a7 6.78kB / 6.78kB                             0.0s
     => => sha256:277539faec26519b55eba0f461b4c12fe4921eb031e80cef0a09b48592cb3eb8 49.81MB / 49.81MB                           4.9s
     => => sha256:2e04e6e2ab16e4be7fa7d604d5ab103338c4620ae546e46a6232bb40e718529c 2.34MB / 2.34MB                             0.5s
     => => sha256:71ddc29abe1f73926ad0922d41b7ad1942fda9be78eeb79f04dc872a10264b67 450B / 450B                                 0.7s
     => => sha256:8e015de364a2eb2ed7c52a558e9f716dcb615560ffd132234087c10ccc1f2c63 1.43kB / 1.43kB                             0.0s
     => => sha256:807e66e2bee193961c9642bb1157d77a61747bf76737ca786da45b10749dcb42 1.16kB / 1.16kB                             0.0s
     => => extracting sha256:277539faec26519b55eba0f461b4c12fe4921eb031e80cef0a09b48592cb3eb8                                  1.8s
     => => extracting sha256:2e04e6e2ab16e4be7fa7d604d5ab103338c4620ae546e46a6232bb40e718529c                                  0.1s
     => => extracting sha256:71ddc29abe1f73926ad0922d41b7ad1942fda9be78eeb79f04dc872a10264b67                                  0.0s
     => [frontend internal] load build context                                                                                 0.1s
     => => transferring context: 818.12kB                                                                                      0.0s
     => [frontend 2/6] WORKDIR /app                                                                                            0.7s
     => [frontend 3/6] RUN npm install @vue/cli@5.0.8 -g                                                                      57.7s
     => [frontend 4/6] COPY package.json .                                                                                     0.1s
     => [frontend 5/6] COPY package-lock.json .                                                                                0.1s
     => [frontend 6/6] RUN npm install                                                                                        13.0s
     => [frontend] exporting to image                                                                                          3.3s
     => => exporting layers                                                                                                    3.3s
     => => writing image sha256:669b7b3220fb165a6e175a62d1df5ac85d46b9a1a2b240ecb0f66523fa22f1cd                               0.0s
     => => naming to docker.io/library/fastapi-vue-frontend                                                                    0.0s
    [+] Running 2/2
     ✔ Container fastapi-vue-frontend-1  Started                                                                               2.7s
     ✔ Container fastapi-vue-backend-1   Running                                                                               0.0s
    sangbinlee9@master:~/fastapi-vue$



![image](https://github.com/sangbinlee/install-docker-nginx/assets/4024414/50fed89e-4c63-4cc2-bd33-7f3cf8af4f4d)



# mkdir postgres_data    
#  docker-compose.yml:



    
    version: '3.8'
    
    services:
    
      backend:
        build: ./services/backend
        ports:
          - 5000:5000
        environment:
          - DATABASE_URL=postgres://hello_fastapi:hello_fastapi@db:5432/hello_fastapi_dev
        volumes:
          - ./services/backend:/app
        command: uvicorn src.main:app --reload --host 0.0.0.0 --port 5000
        depends_on:
          - db
    
      frontend:
        build: ./services/frontend
        volumes:
          - './services/frontend:/app'
          - '/app/node_modules'
        ports:
          - 8081:8081
    
      db:
        image: postgres:latest
        expose:
          - 5432
        environment:
          - POSTGRES_USER=hello_fastapi
          - POSTGRES_PASSWORD=hello_fastapi
          - POSTGRES_DB=hello_fastapi_dev
        volumes:
          - ./postgres_data:/var/lib/postgresql/data/










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
