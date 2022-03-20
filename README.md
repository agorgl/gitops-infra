# gitops-infra

Deploys a gitops infrastructure in k8s, with the help of helm charts and helmfile.  
For a quickstart, copy and modify `.env.sample.yaml` to `.env.default.yaml` and run `helmfile apply`.

## Notes

Create the namespace for workflows:
```
kubectl create namespace workflows
```

To get the auth token for argo workflows run:
```
kubectl -n gitops exec $(kubectl -n gitops get pod -l app.kubernetes.io/instance=argo-workflows,app.kubernetes.io/component=server -o name) -- argo auth token
```
