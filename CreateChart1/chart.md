# Create Chart 

## 내장 객체, 변수 주입 우선순위, 사용자 정의 변수

### 1. Helm Command

```
[Chart Template 생성]
helm create mychart

[Show Command]
helm show values .
helm show chart .
helm show readme .
helm show all .

readme 명령어는 README.md 가 있어야 확인가능

[Template Command]
helm template mychart . 

[Chart 배포]
helm install mychart .

[Get command]
helm get manifest mychart
helm get notes mychart
helm get values mychart
helm get all mychart

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

### 2. 
