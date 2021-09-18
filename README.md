# ckad-personal-resources
load specific version ov kubectl for linux:

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.21.1/bin/linux/amd64/kubectl  && chmod +x kubectl && mv kubectl /usr/bin 
```


Completion:

```bash
echo 'source <(kubectl completion bash | sed s/kubectl/k/g)' >>~/.bashrc
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -F __start_kubectl k' >>~/.bashrc
```

Down
List of alias and functions to to be more easy to work with kubectl.

```bash

export CMD=" -- /bin/sh -c "
export OUT=" --dry-run=client -o yaml "
export DEL="  --grace-period=0 --force "
alias create="k create --record -f "
alias context="k config set-context --current --namespace "

```
TMUX

```bash
ctrl+b+shift+2  -> create new subStection
ctrl+b :resize-pane -D 15  -> reduce the current section

```


Utilities:
```bash

k get events --all-namespaces | grep -iv node      # Show the modiofications related with all objects except Nodes. 

```
