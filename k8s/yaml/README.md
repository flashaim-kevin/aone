# Pod

Pod like a dokcer-compose.yml. A Pod can have many container.

## create

* kubectl create -f my-first-pod.yaml
* kubectl get pod
* kubectl describe pod
* kubectl delete pod my-pod

## 如何與 Pod 中的 container 互動

### kubectl port-forward

* kubectl port-forward my-pod 8081:8080
* http://localhost:8081/ping

### 建立一個 Service

* kubectl expose
  `kubectl expose pod my-pod --type=NodePort --name=my-pod-service`

* kubtctl get service

* minikube service my-pod-service --url