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

```
echo "Hello World!" >> README.md
git status
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/3.png)
```
git diff
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/4.png)

```
git add README.md
git diff --staged
git status
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/6.png)
```
git commit -m 'First commit'
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/7.png)
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/8.png)
```
git remote set-url origin https://killakazzak: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@github.com/killakazzak/netology.git
git push origin main
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/9.png)

[Ссылка на commit](https://github.com/killakazzak/netology/commit/22f3d2506c1b15c3ab6f0682a188c405f8e54892)

---

### Задание 2

```
touch .gitignore
git status
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/21.png)
```
git add .gitignore
git status
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/22.png)
```
echo "*.pyc" >> .gitignore && echo "cache/" >> .gitignore
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/23.png)
```
git add .gitignore
git commit -m "Second Commit"
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/24.png)
```
git push origin main
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/25.png)

[Ссылка на README.md](https://github.com/killakazzak/netology/blob/0d2269d19d0a4587a9e5c471208812acfdc84ecc/README.md)

### Задание 3
```
git branch dev
git checkout dev
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/31.png)
```
echo "Всем привет!" > test.sh
git add test.sh
git commit -m "Commit message"
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/32.png)
```
git checkout main
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/33.png)
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/34.png)

```
git merge dev
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/35.png)
```
git pull
git push
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/36.png)

[Ссылка на граф](https://github.com/killakazzak/netology/network)
### Задание 4
```
git branch conflict
git checkout conflict
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/41.png)
```
git add test.sh
git commit -m "conflict commit"
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/42.png)
```
git push origin conflict
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/43.png)
```
git add test.sh
git commit -m "commit temp"
git push origin main
git merge conflict
git add test.sh
git commit -m "Resolved conflict in test.sh"
git push origin main
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/44.png)
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/45.png)

[Ссылка на файл test.sh](https://github.com/killakazzak/netology/blob/main/test.sh)




