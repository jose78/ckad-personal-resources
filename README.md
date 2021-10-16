# ckad-personal-resources
load specific version of kubectl (1.21) for linux:

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.21.1/bin/linux/amd64/kubectl  && chmod +x kubectl && mv kubectl /usr/bin 
```


List of Completion, aliases and exports to be more faster:

```bash
echo 'source <(kubectl completion bash | sed s/kubectl/k/g)' >>~/.bashrc
echo 'source <(helm completion bash)' >>~/.bashrc
echo 'source <(podman completion bash)' >>~/.bashrc
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -F __start_kubectl k' >>~/.bashrc
export CMD=" -- /bin/sh -c "
export OUT=" --dry-run=client -o yaml "
export DEL="  --grace-period=0 --force "
alias create="k create --record -f "
alias context="k config set-context --current --namespace "
alias cat='pygmentize -g'

```

Utilities:
```bash

k get events --all-namespaces -w -o wide | grep -iv node      # Show the modiofications related with all objects except Nodes. 

```


### Links:
  * [TMUX](https://tmuxcheatsheet.com/)
  * [kubectl cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
  * [Be faster](https://faun.pub/be-fast-with-kubectl-1-18-ckad-cka-31be00acc443)
  * [Tips and complex exercises](https://codeburst.io/kubernetes-ckad-weekly-challenges-overview-and-tips-7282b36a2681)
  * [Some exercisaes in katakoda](https://dev.to/liptanbiswas/ckad-practice-questions-4mpn)

### Little tips:

*  For your convenience, all environments, in other words, the base system and the cluster nodes, have the following additional command-line tools pre-installed and pre-configured:

   * kubectl with kalias and Bash autocompletion
   * jq for YAML/JSON processing
   * tmux for terminal multiplexing
   * curl and wget for testing web services
   * man and man pages for further documentation



### The exam has changed, it have this structure and topics:


 * Application Design and Build – 20%

   *  Define, build and modify container images
   *  Understand Jobs and CronJobs
   *  Understand multi-container Pod design patterns (e.g. sidecar, init and others)
   *  Utilize persistent and ephemeral volumes

 * Application Environment, Configuration and Security – 25%

   *  Discover and use resources that extend Kubernetes (CRD)
   *  Understand authentication, authorization and admission control
   *  Understanding and defining resource requirements, limits and [quotas](https://katacoda.com/pso-sander-van-vugt/scenarios/sander-cka-quota)
   *  Understand ConfigMaps
   *  Create & consume Secrets
   *  Understand ServiceAccounts
   *  Understand SecurityContexts

 * Application Deployment – 20% 

   *  [Use Kubernetes primitives to implement common deployment strategies (e.g. blue/green or canary)](https://harness.io/blog/blue-green-canary-deployment-strategies/)
   *  Understand Deployments and how to perform rolling updates
   *  Use the Helm package manager to deploy existing packages

 * Services and Networking – 20%

   *  Demonstrate basic understanding of NetworkPolicies
   *  Provide and troubleshoot access to applications via services
   *  [Use Ingress rules to expose applications](https://kubernetes.io/docs/concepts/services-networking/ingress/#ingress-rules)

 * Application Observability and Maintenance – 15%

   *  Understand API deprecations
   *  Implement probes and health checks
   *  Use provided tools to monitor Kubernetes applications
   *  Utilize container logs
   *  Debugging in Kubernetes




### External resources:
 
  * [multiple scenarios of katacoda to cover some points](https://katacoda.com/pso-sander-van-vugt)
