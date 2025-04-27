## Project Overview
This repository contains a set of minimal Kubernetes manifests intended to test Argo CD’s ability to deploy and synchronize plain-YAML applications (GitOps). By pointing Argo CD at this repo, you can verify that:

- Pods (and Services) are created as defined  
- NodePort routing works without LoadBalancers or Ingress controllers  
- Basic container commands, probes and multi-container workflows function as expected  

## What’s Deployed

1. **nginx-test** Pod + **nginx-nodeport** Service  
   - Nginx server on port 80, exposed externally on `<NodeIP>:30080` (NodePort)  
2. **busybox-sleep** Pod  
   - Sleeps for 3600 s; useful for exec/debug tests  
3. **busybox-multicmd** Pod  
   - Prints “hello” every 10 s; demonstrates `command` vs `args` usage  

