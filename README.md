# crossplane-landing-zone
A landing zone creation with Crossplane for Platform Engineers


## Setup the cluster

This setup considers that you already have an EKS cluster running and will only install what is
required for the walkthrough:

* crossplane
* crossplane provider-kubernetes and provider-aws
* external secret operator

The products are installed through their respective quickstart methods and **ARE NOT** production ready.

To proceed with the install:

```
$ cd init
$ make install
```

## Deploy the LandingZone Custom Resource

```
# Deploy the XRD
$ kubectl apply -f landing-zone-xrd.yaml

# Deploy the Composition
$ kubectl apply -f landing-zone-composition.yaml

# Deploy a landing zone
# This can be done multiple times by deploying landing zones with different names (edit the manifest)
$ kubectl apply -f landing-zone-claim.yaml
```
