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

```
git config --global user.name "Denis Ten"
git config --global user.email "denis.a.ten@gmail.com"
git status
```
![](https://github.com/killakazzak/8-1-git-hw/blob/main/img/2.png)
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




