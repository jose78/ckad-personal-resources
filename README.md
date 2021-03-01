# ckad-personal-resources

List of alias and functions to to be more easy to work with kubectl.

```
alias k="kubectl "
ns_set(){
  echo "current NS $1"
  export NS=$1
}
ns_create(){
 export NS=$1
 echo "Creating ns $1 $NS"
 k create ns $1
}

pod_get(){
  echo "namespace:$NS"
  k get pods -n $NS
}

pod_creatte(){
   echo "Create pod: $@ -n $NS"
   k run --restart=Never  -n $NS $@
}

describe(){
   echo "namespace:$NS"
   k describe -n $NS $@
}

```
