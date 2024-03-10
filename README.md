# Домашнее задание к занятию "`CI/CD`" - `Тен Денис`

### Задание 1

#### Установка jenkins
```
apt-get install default-jre
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key |
sudo tee \
/usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/bdc22f61-944d-40db-bd15-e79e3caa182f)

```
apt install golang-go
```
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/d5db554e-295f-4558-902a-78f6334ee348)



![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/4aee6f44-cbd6-43d6-b2d7-2171f0cec764)
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/fd3e7080-1076-4d3c-b0cd-cea8c634c92a)
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/2e6c778d-e6f6-4944-b826-6c48a57e74ec)

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/a23698ab-657e-4737-a971-f50176eb43fc)

#### Установка Nexus

```
docker run -d -p 192.168.56.10:8081:8081 -p 192.168.56.10:8082:8082 --name nexus -e INSTALL4J_ADD_VM_PARAMS="-Xms512m -Xmx512m -XX:MaxDirectMemorySize=273m" sonatype/nexus3
```
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/548a06ce-c6a6-425a-84cc-c657b298c696)

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/dab72059-9d07-4ed5-a666-d79b1331cd02)


```
Started by user admin
Running as SYSTEM
Building in workspace /var/lib/jenkins/workspace/Freestyle Project
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Freestyle Project/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/killakazzak/8-2-CI-CD-hw.git # timeout=10
Fetching upstream changes from https://github.com/killakazzak/8-2-CI-CD-hw.git
 > git --version # timeout=10
 > git --version # 'git version 2.25.1'
 > git fetch --tags --force --progress -- https://github.com/killakazzak/8-2-CI-CD-hw.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 223dbc3f489784448004e020f2ef224f17a7b06d (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
Commit message: "Update README.md"
 > git rev-list --no-walk 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
[Freestyle Project] $ /bin/sh -xe /tmp/jenkins2132550711709978702.sh
+ go test .
ok  	github.com/netology-code/sdvps-materials	(cached)
+ docker build . -t 10.159.86.111:8082/hello-world:v32
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 350B 0.1s done
#1 DONE 0.1s

#2 [internal] load metadata for docker.io/library/alpine:latest
#2 DONE 1.1s

#3 [internal] load metadata for docker.io/library/golang:1.16
#3 DONE 1.2s

#4 [internal] load .dockerignore
#4 transferring context: 2B done
#4 DONE 0.0s

#5 [builder 1/4] FROM docker.io/library/golang:1.16@sha256:5f6a4662de3efc6d6bb812d02e9de3d8698eea16b8eb7281f03e6f3e8383018e
#5 DONE 0.0s

#6 [stage-1 1/3] FROM docker.io/library/alpine:latest@sha256:c5b1261d6d3e43071626931fc004f70149baeba2c8ec672bd4f27761f8e1ad6b
#6 DONE 0.0s

#7 [internal] load build context
#7 transferring context: 13.13kB 0.3s done
#7 DONE 0.3s

#8 [stage-1 2/3] RUN apk -U add ca-certificates
#8 CACHED

#9 [builder 2/4] WORKDIR /go/src/github.com/netology-code/sdvps-materials
#9 CACHED

#10 [builder 3/4] COPY . ./
#10 CACHED

#11 [builder 4/4] RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
#11 CACHED

#12 [stage-1 3/3] COPY --from=builder /app /app
#12 CACHED

#13 exporting to image
#13 exporting layers done
#13 writing image sha256:ff7b49af16e5ffe7831162258cc6558462bfebd9b1689c111e920bee16c2bc06 0.0s done
#13 naming to 10.159.86.111:8082/hello-world:v32
#13 naming to 10.159.86.111:8082/hello-world:v32 0.0s done
#13 DONE 0.1s
+ docker login 10.159.86.111:8082 -u admin -p admin
WARNING! Using --password via the CLI is insecure. Use --password-stdin.
WARNING! Your password will be stored unencrypted in /var/lib/jenkins/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
+ docker push 10.159.86.111:8082/hello-world:v32
The push refers to repository [10.159.86.111:8082/hello-world]
11bcb0fc846e: Preparing
73ced805857e: Preparing
d4fc045c9e3a: Preparing
73ced805857e: Layer already exists
11bcb0fc846e: Layer already exists
d4fc045c9e3a: Layer already exists
v32: digest: sha256:d5e57f08b444e1939777680fd2c3b95a55719a4d293600b32a5a20e896ee05c2 size: 950
+ docker logout
Removing login credentials for https://index.docker.io/v1/
Finished: SUCCESS
```

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/4ddaed8b-0b36-4730-bef6-e74de2b23629)



### Задание 2

```
pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git branch: 'main', url:'https://github.com/killakazzak/8-2-sdvps-materials-hw.git'}
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'docker build . -t 10.159.86.111:8082/hello-world:v$BUILD_NUMBER'
   }
  }
  stage('Push') {
   steps {
    sh 'docker login 10.159.86.111:8082 -u admin -p admin && docker push 10.159.86.111:8082/hello-world:v$BUILD_NUMBER && docker logout'   }
  }
 }
}
```
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/394fdf8f-8a8e-42dc-9eb9-3931a20b410b)

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/17e9621e-5822-4d97-855c-fb25009d4dbb)







### Задание 3

#### Установка Nexus

```
docker run -d -p 192.168.56.10:8081:8081 -p 192.168.56.10:8082:8082 --name nexus -e INSTALL4J_ADD_VM_PARAMS="-Xms512m -Xmx512m -XX:MaxDirectMemorySize=273m" sonatype/nexus3
```
![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/548a06ce-c6a6-425a-84cc-c657b298c696)

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/f3fbafda-ede3-4f95-bfc1-eaf587a1f138)

```
pipeline {
 agent any
 stages {
  stage('Git') {
   steps {
    git branch: 'main', url:'https://github.com/killakazzak/8-2-CI-CD-hw.git'
   }
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'go build -o app .'
   }
  }
  stage('Push') {
   steps {
    sh 'curl -u admin:admin --upload-file app "http://10.159.86.111:8081/repository/my_raw_repo/hello-world/hello-world-$BUILD_NUMBER"'
   }
  }
 }
}
```

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/31d3e88c-61e9-4c51-a41a-37a3598f44ad)

![image](https://github.com/killakazzak/8-2-ci-cd-hw/assets/32342205/aa1ffac7-ce35-4732-afd0-7a5c376b59d5)



### Задание 4




