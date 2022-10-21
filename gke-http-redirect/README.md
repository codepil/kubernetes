# gke-https-redirect
Demonstration how to use the newly introduced https redirect support in native GKE ingress resources (GCLB).


## Requirements

### GKE version

As mentioned in the article, your GKE cluster needs to be running at least a recent version 1.17-gke for this to work.

### Named IP address

You will need a static reserved ip address going by the name of `gke-https-redirect`. Create it like this:

```
gcloud compute addresses create gke-https-redirect --global
```

### DNS Names

You will want to override the domain names listed in `managedcertificate.yaml`. Also make sure they exist and point to the IP adress you created above.

## Installation

```
kubectl apply -f k8s/
```

---
