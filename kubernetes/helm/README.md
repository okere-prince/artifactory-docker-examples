# Artifactory in Kubernetes using Helm package manager
This directory has examples for Artifactory in Kubernetes deployments using the [Helm](https://helm.sh/) package manager.

## Helm
From https://helm.sh/:
```
What is Helm?

Helm helps you manage Kubernetes applications — Helm Charts helps you define, install, and upgrade even the most complex Kubernetes application.
```

Helm in [GitHub](https://github.com/kubernetes/helm)

## Deployment

### Installing helm
Follow [instructions on installing helm](https://github.com/kubernetes/helm#install)
 
### Deploying Artifactory
You can deploy the Artifactory chart, which is in the [artifactory](artifactory) directory
```bash
$ helm install -n artifactory ./artifactory
```

You can package the Artifactory chart and distribute it for use later
```bash
$ helm package artifactory/
```

This will create a file `artifactory-<version>.tgz`. You can deploy it to Kubernetes with
```bash
$ helm install -n artifactory ./artifactory-<version>.tgz
```

### Accessing Artifactory
**NOTE:** It might take a few minutes for Artifactory's public IP to become available.
Follow the instructions outputted by the install command to get the Artifactory IP to access it.

### Updating Artifactory
Once you have a new chart version, you can update your deployment with
```bash
$ helm upgrade -n artifactory ./artifactory
```

This will apply any configuration changes on your existing deployment.

See more details on [using helm](https://github.com/kubernetes/helm/blob/master/docs/using_helm.md).
