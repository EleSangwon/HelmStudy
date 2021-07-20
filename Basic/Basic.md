# Study Helm 
## 1-1. Install Helm

```
공식 사이트 : https://github.com/helm/helm/releases/

Linux 기준 설치방법
curl -O https://get.helm.sh/helm-v3.6.2-linux-amd64.tar.gz
tar -zxvf helm-v3.6.2-linux-amd64.tar.gz
mv linux-amd64/helm /usr/local/bin/helm
```

## 1-2. 키워드 자동완성

```
source <(helm completion bash)

Linux:
helm completion bash > /etc/bash_completion.d/helm 
```

## 1-3. 버전 확인
```
helm version
```

## 1-4. K8S Config 파일 확인
```
cd ~/.kube/
```

# Chart Repository 

## 2-1. 레포지토리 등록
```
Artifact Hub : https://artifacthub.io/

[ 등록 ]
helm repo add bitnami https://charts.bitnami.com/bitnami

[ 조회 ] 
helm repo list

[ Chart Search ]
helm search repo bitnami | grep tomcat 

[ Update ] 
helm repo update

[ Delete ]
helm repo remove bitami
```
![basic1](https://user-images.githubusercontent.com/50174803/126292199-9d983740-191f-4e51-8ebc-fd8b7944d827.PNG)

## 2-2. Tomcat 배포
```
[ 배포 ]
helm install sangwon-tomcat bitnami/tomcat --version 9.1.0 --set persistence.enabled=false

[ 결과 확인 및 접속 ]
kubectl get svc sangwon-tomcat
```
![basic2](https://user-images.githubusercontent.com/50174803/126292272-4942b1c9-da95-4818-b1c3-bbe3afaad436.png)
![basic3](https://user-images.githubusercontent.com/50174803/126292298-30cab357-8a86-4704-b448-cf137180c4e2.png)

## 2-3. Tomcat 삭제
```
[ 배포 리스트 조회 ]
helm list

[ 배포 상태확인 ]
helm status sangwon-tomcat

[ 삭제 ]
helm uninstall sangwon-tomcat

[ 리소스 확인 ]
kubectl get all
```
![basic4](https://user-images.githubusercontent.com/50174803/126292348-3d8fa01a-b808-4d82-9789-a3f2b8ccbfaa.png)

# Tomcat Chart 다운로드 & 배포

## 3-1. Chart Download
```
[ Download ]
helm pull bitnami/tomcat --version 9.1.0

[ 압축 풀기 ]
tar -xf ./tomcat-9.1.0.tgz

[ 배포 ]
helm install sangwon-tomcat . -f values.yaml

[ 결과 확인 및 접속 ]
kubectl get svc sangwon-tomcat 
```
![basic5](https://user-images.githubusercontent.com/50174803/126292379-f5a114cd-72a1-48f4-ac3f-0b62675f3d30.png)
