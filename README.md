# kubernetes-example-voting-app
Deploy Docker's example voting app on Kubernetes

Create in the following order:
kubectl create -f redis-pod.yml
kubectl create -f redis-service.yml
kubectl create -f postgres-pod.yml
kubectl create -f postgres-service.yml
kubectl create -f working-app-pod.yml
kubectl create -f result-app-pod.yml
kubectl create -f result-app-service.yml
kubectl create -f voting-app-pod.yml
kubectl create -f voting-app-service.yml

$ kubectl get pods
NAME             READY   STATUS    RESTARTS   AGE
postgres-pod     1/1     Running   0          16m
redis-pod        1/1     Running   0          18m
result-app-pod   1/1     Running   0          7m8s
voting-app-pod   1/1     Running   0          36s
worker-app-pod   1/1     Running   0          14m

$ kubectl get services
NAME             TYPE           CLUSTER-IP      EXTERNAL-IP      PORT(S)        AGE
db               ClusterIP      10.19.248.23    <none>           5432/TCP       16m
kubernetes       ClusterIP      10.19.240.1     <none>           443/TCP        137m
redis            ClusterIP      10.19.253.47    <none>           6379/TCP       18m
result-service   LoadBalancer   10.19.251.108   34.67.141.216    80:30990/TCP   4m1s
voting-service   LoadBalancer   10.19.240.11    35.184.223.239   80:30514/TCP   58s


