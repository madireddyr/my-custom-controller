Ref : https://infoheap.com/mac-m1-install-kubernetes-wiht-kind/


```brew install --cask virtualbox```


```brew install --cask docker```


```open -a Docker```


```brew install kind```

```kind create cluster```


```
rmadireddy@Ravis-MacBook-Pro ~ % brew install kind
==> Downloading https://formulae.brew.sh/api/formula.jws.json
################################################################################################################################################################################################################## 100.0%
==> Downloading https://formulae.brew.sh/api/cask.jws.json
################################################################################################################################################################################################################## 100.0%
Warning: kind 0.20.0 is already installed and up-to-date.
To reinstall 0.20.0, run:
  brew reinstall kind
rmadireddy@Ravis-MacBook-Pro ~ % kind create cluster
Creating cluster "kind" ...
 ✓ Ensuring node image (kindest/node:v1.27.3) 🖼 
 ✓ Preparing nodes 📦  
 ✓ Writing configuration 📜 
 ✓ Starting control-plane 🕹️ 
 ✓ Installing CNI 🔌 
 ✓ Installing StorageClass 💾 
Set kubectl context to "kind-kind"
You can now use your cluster with:

kubectl cluster-info --context kind-kind

Have a nice day! 👋
rmadireddy@Ravis-MacBook-Pro ~ % kind get clusters 
kind
rmadireddy@Ravis-MacBook-Pro ~ % brew install kubectl 
==> Downloading https://ghcr.io/v2/homebrew/core/kubernetes-cli/manifests/1.28.2
######################################################################################################################################################################################################################## 100.0%
==> Fetching kubernetes-cli
==> Downloading https://ghcr.io/v2/homebrew/core/kubernetes-cli/blobs/sha256:1c9fc80e17d7f48d3f736075e803356d2a3382e3791739f2f53f931d61b92e10
######################################################################################################################################################################################################################## 100.0%
==> Pouring kubernetes-cli--1.28.2.arm64_sonoma.bottle.tar.gz
==> Caveats
zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
==> Summary
🍺  /opt/homebrew/Cellar/kubernetes-cli/1.28.2: 232 files, 58.8MB
==> Running `brew cleanup kubernetes-cli`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
rmadireddy@Ravis-MacBook-Pro ~ % kubectl cluster-info --context kind-kind
Kubernetes control plane is running at https://127.0.0.1:62245
CoreDNS is running at https://127.0.0.1:62245/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
rmadireddy@Ravis-MacBook-Pro ~ % kind get clusters
kind
rmadireddy@Ravis-MacBook-Pro ~ % kubectl version --client --output=yaml 
clientVersion:
  buildDate: "2023-05-17T14:20:07Z"
  compiler: gc
  gitCommit: 7f6f68fdabc4df88cfea2dcf9a19b2b830f1e647
  gitTreeState: clean
  gitVersion: v1.27.2
  goVersion: go1.20.4
  major: "1"
  minor: "27"
  platform: darwin/arm64
kustomizeVersion: v5.0.1

rmadireddy@Ravis-MacBook-Pro ~ % kubectl cluster-info
Kubernetes control plane is running at https://127.0.0.1:62245
CoreDNS is running at https://127.0.0.1:62245/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
rmadireddy@Ravis-MacBook-Pro ~ % kubectl config use-context kind-kind-2
error: no context exists with the name: "kind-kind-2"
rmadireddy@Ravis-MacBook-Pro ~ % kubectl get pods -n kube-system
NAME                                         READY   STATUS    RESTARTS   AGE
coredns-5d78c9869d-5zx5b                     1/1     Running   0          69s
coredns-5d78c9869d-dh8nf                     1/1     Running   0          69s
etcd-kind-control-plane                      1/1     Running   0          84s
kindnet-v2bz6                                1/1     Running   0          69s
kube-apiserver-kind-control-plane            1/1     Running   0          84s
kube-controller-manager-kind-control-plane   1/1     Running   0          84s
kube-proxy-nhl8w                             1/1     Running   0          69s
kube-scheduler-kind-control-plane            1/1     Running   0          84s
rmadireddy@Ravis-MacBook-Pro ~ % kubectl get namespace
NAME                 STATUS   AGE
default              Active   94s
kube-node-lease      Active   94s
kube-public          Active   94s
kube-system          Active   94s
local-path-storage   Active   90s
rmadireddy@Ravis-MacBook-Pro ~ % 
```


``` brew install stefanprodan/tap/timoni ```