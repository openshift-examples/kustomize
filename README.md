# Kustomize examples

```
oc apply -k git@github.com:openshift-examples/kustomize/components/simple-http-server
```

## Remote examples

```yaml
bases:
- git@github.com:pipe-cd/manifests.git/kustomization/helloworld?ref=v0.1.2-15

namePrefix: kustomize-remote-base-

commonLabels:
  app: kustomize-remote-base-helloworld

images:
- name: gcr.io/pipecd/helloworld
  newTag: v0.10.0

components:
  - git@github.com:openshift-examples/kustomize.git/components/agnhost?ref=2025-06-25
  - git@github.com:openshift-examples/kustomize.git/components/rhel-support-tools/?ref=2025-06-25
  - git@github.com:openshift-examples/kustomize.git/components/simple-http-server/?ref=2025-06-25
  - git@github.com:openshift-examples/kustomize.git/components/simple-httpd-vm/?ref=2025-06-25
```
[Source](https://github.com/pipe-cd/examples/blob/master/kubernetes/kustomize-remote-base/kustomization.yaml)


