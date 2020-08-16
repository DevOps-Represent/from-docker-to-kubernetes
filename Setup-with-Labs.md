# Setting up with Labs

To setup with the Play with Kubernetes environment, simply login [to the Labs website with your Github or Dockerhub credentials](http://labs.play-with-k8s.com/).

*NOTE: This option comes with a little bit of risk as it can sometimes not work and your virtual environment lasts 4 hours before being destroyed* ☠️


Once logged in, we'll need to go through a couple of steps:

### Create two instances

First, we need to create two instances using the *Add New Instance* button. The first one will function as our *"master"* (**Terminal 1**), and the second will function as our *"worker node"* (**Terminal 2**).

On *Terminal 1*, we'll initialize the cluster with this command:

```
kubeadm init --apiserver-advertise-address $(hostname -i)
```

This will take a while, but you should see something like this at the end:

```
  You can now join any number of machines by running the following on each node
  as root:

  kubeadm join --token SOMETOKEN SOMEIPADDRESS --discovery-token-ca-cert-hash SOMESHAHASH
```

Copy the line that starts with `kubeadm join` and paste it into **Terminal 2**. Once this finishes, you should see something like:

```
Node join complete:
* Certificate signing request sent to master and response
  received.
* Kubelet informed of new secure connection details.
```

This means you're almost done! The last step is to initialize cluster networking in **Terminal 1** - with this command:

```
kubectl apply -n kube-system -f \
 "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 |tr -d '\n')"
```

To check if everything's running fine, run the following on **Terminal 1**:

```
kubectl get nodes
```

This should show a list of both *master* and *worker* nodes showing as *Ready*. Aaaand you're done! All commands from here on need to be executed from **Terminal 1**.
