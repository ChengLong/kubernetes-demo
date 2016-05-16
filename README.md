## Orchestrating Docker with Kubernetes

This is a demo app to showcase orchestrating Docker with Kubernetes. You can find more at [my post](https://chengl.com/orchestrating-docker-with-kubernetes/).

### Usage

1. Run backend

  ```
  kubectl create -f backend.yaml
  ```
2. Run frontend

  ```
  kubectl create -f frontend.yaml
  ```

3. Self-healing

  Delete a random pod and see Kubernetes creates a new one.
  ```
  kubectl delete pod frontend-2747139405-bk4ul; kubectl get pods
  ```

4. Scaling

  ```
  kubectl scale deployment/frontend --replicas=6; kubectl get pods
  ```

5. Rolling update
  ```
  kubectl create -f frontend-canary.yaml
  vim frontend.yaml # update simple-node:v1 to simple-node:v2
  kubectl apply -f frontend.yaml
  ```

