### Reflection Hello Minikube

1. 
Screenshot 1:
![alt text](<assets/Screenshot (1115).png>)

Screenshot 2:
![alt text](<assets/Screenshot (1114).png>)

Answer:
Yes, the number of logs increased each time the app is opened after exposing the application as a Service. Before exposing, the logs would only show activity that is related to the Pod itself as can be seen in screenshot 1. However, after exposing the application as a Service now the logs show additional entries for each incoming request to the Service as can be seen in screenshot 2. This is because when opening the app several times while the proxy into the Service is running, new log entries in the Pod logs for each request would be made. This would mean that the number of logs will increase each time the app is opened and as each of those request generates a new log entry.

2. Since there are two versions of kubectl get invocation in this tutorial, the first one does not have any option but the second one has -n option with value set to kube-system. The purpose for this -n option and why did the output not list the pods/services that were explicitly created was because the -n option in kubectl is used to specify the namespace in which the operation should be performed. So when the first kubectly get command was executed, it was for the default namespace where the resources were created. The second one however, lists the resources in the kube-system namespace, which is a reserved namespace used by Kubernetes for system components and services. So basically this namespace does not have the Pods and Services that were created, as those resources are in the default namespace. For additional information, based on the Kubernetes documentation for Namespaces, modification to the kube-system namespace is often avoided or even creation inside of it as it is meant for Kubernetes system components. Well that is also why the created resources for Pods, Services, ect in the tutorial were created in the default namespace in the first place. 