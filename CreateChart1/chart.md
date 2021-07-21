# Create Chart 

## 내장 객체, 변수 주입 우선순위, 사용자 정의 변수

### 1. Helm Command
![chart0](https://user-images.githubusercontent.com/50174803/126429085-d124d3dc-fdea-44e0-8f67-33ab332b0d74.PNG)

```
[Chart Template 생성]
helm create mychart

[Show Command]
helm show values .
helm show chart .
helm show readme .
helm show all .

readme 명령어는 README.md 가 있어야 확인가능
```
![chart1](https://user-images.githubusercontent.com/50174803/126429106-50de8e47-b9e8-4566-adc9-75f71f4c4c51.PNG)
![chart2](https://user-images.githubusercontent.com/50174803/126429157-db8d849c-b475-4c8e-9637-496e4768ac1a.PNG)
```
[Template Command]
helm template mychart . 
```
![chart3](https://user-images.githubusercontent.com/50174803/126429167-4259cab0-7b90-4431-a68e-c63291a5c56f.PNG)


![chart4](https://user-images.githubusercontent.com/50174803/126429259-c46d48b9-fdc5-420e-b7d3-e9a5a6529d69.PNG)
```
[Chart 배포]
helm install mychart .
```

```
[Get command]
helm get manifest mychart
helm get notes mychart
helm get values mychart
helm get all mychart
```
![chart6](https://user-images.githubusercontent.com/50174803/126429317-ae6fa736-6746-4243-86fb-9ce21c2e2200.PNG)
```
[helm install -f value , set 비교]
kubectl get pods 
--> Pod 1개 생성 (  defalut로 values.yaml에 replicaCount=1 )
vi values.yaml --> replicaCount=2 로 수정

helm uninstall mychart 
helm install mychart . -f values.yaml 
--> Pod 2개 생성됨

helm install mychart . --set replicaCount=3
--> Pod 3개 생성됨 
values에 replica는 2지만 set 이 더 우선적으로 작용
```
![chart7](https://user-images.githubusercontent.com/50174803/126429341-71a7360c-f93f-49da-9bba-dade39fedc5c.PNG)
![chart8](https://user-images.githubusercontent.com/50174803/126429353-039ecbb1-dcd6-4dd5-aa77-fd5ce96c69f5.PNG)
### 2. 
