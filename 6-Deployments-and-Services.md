# Services and Deployments

So the pod is up, now how do we access it?

In Kubernetes, there is an object type called a `service` which functions as a load balancer. What this means is that if someone needs to talk to or access a `Pod`, then they need to go through the `Service`.

We can create a service for your pod with the following command:

```
kubectl expose pod devopsgirls-pod --port=8000 --targetport=80 --name devopsgirls-service --type LoadBalancer
```

We can check if your service exists by listing them out, the same way we list out our pods:

```
kubectl get services
```

Which should give you an output that's similar to below:

```
$ kubectl get service
NAME                    TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
devopsgirls-service     ClusterIP   10.105.91.242    <none>        8000/TCP   5s
```

We can now access the services of your pod!

 - If you're running this workshop using `minikube`, then use the following command to see the URL you can use in your browser to access it:

```
minikube service --url devopsgirls-service
```
 
 - If you're running this workshop using *Play-with-k8s*, simply run the following command on Terminal 1:

```
curl <cluster IP>
```

Now, to remove the service, we simply delete the `service` object just as we do any other object in Kubernetes:

```
kubectl delete service devopsgirls-service
```

Additionally, we can also use YAML to deploy the service. We can use the file at `kubes/service.yaml`, and run:

```
kubectl apply -f kubes/service.yaml
```

Again, we can check if the service exists using this command:

```
kubectl get service
```

### Deployments

As nice as it is that we can use a singular service to talk to things. But what happens when we delete a pod? Well, we can just tear it down and see what happens, right?

```
kubectl delete pod devopsgirls-pod
```

Now, try accessing the service again using the instructions above. Spoiler: it's not gonna work! Just as we need high availability for the applications we put out on the web, we need to make sure that our pods are highly available. So here come **deployments**.

Creating a deployment

Listing the deployment

Listing the pods "inside" a deployment

Removing a pod inside a deployment

