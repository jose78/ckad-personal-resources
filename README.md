# ckad-personal-resources
load specific version ov kubectl for linux:

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.21.1/bin/linux/amd64/kubectl  && chmod +x kubectl && mv kubectl /usr/bin 
```


Completion:

```
kubectl completion bash | sed s/kubectl/k/g >/etc/bash_completion.d/kubectl
alias k='printf "\n\n" && cat ~/.kube/config | grep "current-context:" --color&& printf "\n"  && kubectl'
complete -F __start_kubectl k
```

Down
List of alias and functions to to be more easy to work with kubectl.

```bash

export OUT=" --dry-run=client -o yaml "
export DEL="  --grace-period=0 --force "


function k_pod(){ 
  echo "pod name: $1"
  echo "pod image: $2"
  echo "out to file $3"
  cat ~/.kube/config | grep "current-context:" --color
        kubectl run $1 --image=$2  --restart=Never $OUT > $3
}

function k_pod_sh(){
  echo "pod name: $1"
  echo "pod image: $2"
  echo "pod sh command: $4"
  echo "out to file $3"
  cat ~/.kube/config | grep "current-context:" --color
  kubectl run $1 --image=$2  --restart=Never $OUT -- /bin/sh -c "$4" > $3
}

```
