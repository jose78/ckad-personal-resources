# ckad-personal-resources
load specific version of kubectl (1.21) for linux:

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.21.1/bin/linux/amd64/kubectl  && chmod +x kubectl && mv kubectl /usr/bin 
```


List of Completion, aliases and exports to be more faster:

```bash
echo 'source <(kubectl completion bash | sed s/kubectl/k/g)' >>~/.bashrc
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -F __start_kubectl k' >>~/.bashrc
export CMD=" -- /bin/sh -c "
export OUT=" --dry-run=client -o yaml "
export DEL="  --grace-period=0 --force "
alias create="k create --record -f "
alias context="k config set-context --current --namespace "

```

Utilities:
```bash

k get events --all-namespaces -w -o wide | grep -iv node      # Show the modiofications related with all objects except Nodes. 

```


Links:
  * [TMUX](https://tmuxcheatsheet.com/)
  * [kubectl cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
  * [Be faster](https://faun.pub/be-fast-with-kubectl-1-18-ckad-cka-31be00acc443)
  * [Tips and complex exercises](https://codeburst.io/kubernetes-ckad-weekly-challenges-overview-and-tips-7282b36a2681)
  * [Some exercisaes in katakoda](https://dev.to/liptanbiswas/ckad-practice-questions-4mpn)

Little tips:

*  For your convenience, all environments, in other words, the base system and the cluster nodes, have the following additional command-line tools pre-installed and pre-configured:

   * kubectl with kalias and Bash autocompletion
   * jq for YAML/JSON processing
   * tmux for terminal multiplexing
   * curl and wget for testing web services
   * man and man pages for further documentation


