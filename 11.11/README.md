VirtualBox를 이용한 ubuntu 환경설정

# 1.가상머신 VirtualBox 다운
<img width="800" src="https://user-images.githubusercontent.com/80237293/206605381-4c9c07bf-a58e-443c-9ed5-9c4b670253aa.png" />

# 2.리눅스 OS 우분투 다운
<img width="800" src="https://user-images.githubusercontent.com/80237293/206605387-c7fe83ef-9453-4284-a43c-dea09e29ba92.png"/>

# 3. 우분투 설치를 위한 가상 디스크
새로만들기를 선택해 이름을 설정한 후 다운받은 우분투 ISO 파일을 추가
<img width="800" src="https://user-images.githubusercontent.com/80237293/206605400-1a6ab567-11a4-48bc-912d-0b0830c85882.png"/>

# sudo (substitute user do)
- 현재 계정에서 다른 계정, 즉 슈퍼 유저로서 관리자 권한을 가진 계정으로 프로그램을 구동할 수 있도록 하는 command
- ‘sudo -i’는 root 계정으로 로그인(login)하며 ‘/root’ 디렉터리(directory)로 이동하는 command이고, 
  ‘sudo -s’는 현재 directory를 유지하며 root 계정으로 login 하는 command ‘sudo’, ‘sudo -i’, 
- ‘sudo -s’ command는 현재 계정의 password를 요구하고, 전환된 계정의 환경변수는 적용하지 않음

# 패키지 업데이트
$ sudo apt update
package 인덱스를 update

$ sudo apt upgrade –y
업그레이드 가능한 모든 패키지를 update

# Docker
가상 머신처럼 독립된 실행환경을 만들어주는 것으로, 운영체제를 설치한 것과 유사한 효과를 낼 수 있지만, 
실제 운영체제를 설치하지 않기 때문에 설치 용량이 적고 실행 속도 또한 빠르다.
예전에는 윈도에 VM Ware와 같은 가상 머신을 설치하였으나 최근에는 리눅스 계열에서 Docker가 그 역할을 대신하고 있다.

# 저장소 설정
## 1. HTTPS를 통해 리포지토리를 사용할 수 있도록 패키지 인덱스를 업데이트하고 apt 패키지를 설치
$ sudo apt-get update
$ sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
## 2. 공식 GPG 키 추가
$ sudo mkdir -p /etc/apt/keyrings
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

## 3. 리포지토리 설정
$ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# 도커 엔진 설치
## 1.apt 패키지 색인 업데이트
$ sudo apt-get update

## 2. 엔진, containered 및 compose 설치
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

## 도커 버전 확인
$ sudo docker version
- 도커 버전을 확인하여 클라이언트와 서버가 설치된 것을 확인


