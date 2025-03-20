# Setting a Default Namespace for a Kubectl Context

It's irritating to have to add `--namespace foo` to every `kubectl` command
so here's how to set a default namespace for a context:

```
$ kubectl config set-context rancher-desktop --namespace=foo
```

View the output:

```
$ kubectl config view --minify
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: DATA+OMITTED
    server: https://127.0.0.1:6443
  name: rancher-desktop
contexts:
- context:
    cluster: rancher-desktop
    namespace: foo
    user: rancher-desktop
  name: rancher-desktop
current-context: rancher-desktop
kind: Config
preferences: {}
users:
- name: rancher-desktop
  user:
    client-certificate-data: DATA+OMITTED
    client-key-data: DATA+OMITTED
```
