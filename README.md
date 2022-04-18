# Infrastructure 



## Bootstrap a cluster

Install Fluxcd base controllers:

```
flux install  --components source-controller,kustomize-controller -n flux-system
```

Create GPG Private Key Secret

```
gpg --export-secret-keys --armor "1864E4C5B98548EF9ABCABFB96AE8BF4EF5943DD" |
kubectl create secret generic flux-system-gpg-key \
--namespace=flux-system \
--from-file=sops.asc=/dev/stdin
```





