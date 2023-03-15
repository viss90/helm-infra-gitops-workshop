# helm-infra-gitops-workshop

## Helm template with parameters

Helm template now can be used with parameters of Helm instead of changing values in the _values.yaml_ file. You decide how to work.

For example, looking at the values file, all the modules have been set to **false**. To enable any of these modules without edit the value file, you can run:

```bash
helm template --debug . --set global.nmstate.hostname=ip-10-0-150-255.eu-west-1.compute.internal --set global.nmstate.enabled=true --set global.operators.enabled=true
```

## Deploying with ArgoCD
To deploy any module with ArgoCD, you have two options:

1. Edit the [values file](./values.yaml) and enable the module that you want to deploy.
2. Run helm template with parameters as described in the [section below](#helm-template-with-parameters). An example of ArgoCD application can be found in the file [app.yaml](./examples/argocd/app.yml)