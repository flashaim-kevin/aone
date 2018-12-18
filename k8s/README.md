# K8S

practice how to use.

## 預想情境

K8S 是一各國宅型社區(很多棟)的管理者。每棟國宅(Node)就像(實體機、虛擬機)。國宅中的一戶就是一個(Pod)，每戶有多個人(container)，每個 Pod 是一個對外的最小單位。當其中一棟國宅(Node)太過擁擠時，K8S 會負責把過多的戶(Pod)搬往相對空的大樓。

## Require

### virtualbox

用來建立 node 的虛擬軟體

### kubuctl

* kubectl create
  
* kubectl get

* kubectl describe

* kubectl expose

  可以幫我們創建一個新的 Service 物件，來讓Kubernetes Cluster中運行的 Pod與外部互相溝通。

* kubectl delete

### minikube

* minikube start

* minikube status

* minikube stop

* minikube dashboard