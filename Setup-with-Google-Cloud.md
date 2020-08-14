# Setting up with Google Cloud

We can use Google Kubernetes Engine (GKE) to run our Kubernetes cluster. Google Cloud has a *free tier*, which allows us to run a cluster for free - so long as we turn it off when the workshop ends.

### Signing up for Google Cloud

To sign up for Google Cloud Platform Trial (which includes *300.00 AUD* of credit), simply use your *Gmail* account to sign up using the form at: [https://console.cloud.google.com/freetrial](https://console.cloud.google.com/freetrial)

The trial may prompt you for credit card info - don't worry, we won't be billed if we clean up!

### Setting up a Cluster

Once you're signed up, visit the [Kubernetes engine page](https://console.cloud.google.com/projectselector/kubernetes) in the Google Cloud console. If you don't have a project yet, we can create our project as follows:

![Kubes](/images/11-project-page.png)

Once we select a project, it should start the Kubernetes Engine API. This will take some time - so grab a coffee, relax, and get ready!

![Kubes](/images/11-kube-api.png)

Once this finishes, click on the Google Console button on the top-right of the page. This will enable a web console on the bottom of your screen - where you can type commands to interface with both *Google Cloud* and *Kubernetes*!

![Kubes](/images/11-web-console.png)

On the console, let's set our region. For this workshop, we'll be using `australia-southeast1`:

```
gcloud config set compute/zone australia-southeastl-a
```

After this, all we need to do is create a cluster. Type in the following command to create a single-node cluster called `devops-girls` (Feel free to use any cluster name!):

```
gcloud container clusters create devops-girls --num-nodes=1
```

Like the previous steps, this may take some time - so maybe make another cup of tea. You'll see the Google Cloud console doing a couple of things (which we'll talk about shortly): but once it finishes, the only command left to run is to get the credentials to the cluster:

```
gcloud container clusters get-credentials devops-girls
```

Where `devops-girls` is what you called your cluster. And now you're done!
