# Install-Devstack

## Introduction
* Openstack 설치 방법 정리
  * Ubuntu 18.04
  * devstack v2019.12.10

<br>

## Step

### 1. ssh <br>
* 외부 접속을 위해서 ssh 설치 <br>        
```
$sudo apt-get install -y openssh-server
```

### 2. vim <br>
* vi 설치 <br>        
```
$sudo apt-get -y install vim
```

### 3. git <br>
* git 설치 <br>        
```
$sudo apt-get -y install git
$git clone https://github.com/shhan0226/Install-Devstack.git
```

### 4. sh <br>
* 작성된 .sh를 순서데로 실행 <br>
* 사용자 로그인
```
$/home/사용자/Install-Devstack/setup1.sh
```
* root 로그인
```
$/home/사용자/Install-Devstack/setup2.sh
```
* stack 로그인
```
$/home/사용자/Install-Devstack/setup3.sh
```

### 5. vi local.conf <br>
* 내용을 수정 <br>        
```
[local|localrc]
HOST_IP=127.0.0.1
ADMIN_PASSWORD=secret
DATABASE_PASSWORD=$ADMIN_PASSWORD
RABBIT_PASSWORD=$ADMIN_PASSWORD
SERVICE_PASSWORD=$ADMIN_PASSWORD
```

### 6. Run & Error <br>
* 실행은 stackRun.sh를 이용함 <br>
```
$/home/사용자/Install-Devstack/stackRun.sh
```
* 첫 실행시 .cache 권한 때문에 오류가 발생함<br>
* 오류가 발생할 경우 stackClr.sh를 사용해 한번 지워주고 다시 실행(필요할 경우 오류를 수정)<br>
```
$/home/사용자/Install-Devstack/stackClr.sh
$/home/사용자/Install-Devstack/stackRun.sh
```
* 실행 전, stack 로그인 필요
```
$su - stack
```
