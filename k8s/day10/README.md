# Day10

## start

1. kubectl create -f my-pod.yaml
2. kubectl get pods [--show-labels]
3. kubectl expose pod my-pod --type=NodePort --name=my-pod-servcie
4. minikube service my-pod-service --url

> Kubernetes Cluster 內部會有一套網路系統，會替每個 Pod 建立一個 Cluster IP，這個 IP 是由 Kubernetes 內部隨機產生的。這個 Cluster IP 只有Cluster內部資源可以使用；外部資源是無法透過 Cluster IP 與 Pods 互動，所以我們需要再建立一個 Service 元件作為一個橋樑，讓 Cluster 以外的服務也可以與 Pod 做互動。