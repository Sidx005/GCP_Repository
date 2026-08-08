Absolutely. Here are **40 GKE MCQs**, progressing from **basic → intermediate → advanced → production case studies**, with the **answer immediately below each question**.

## GKE MCQs — Basic to Advanced

### 1. What does GKE stand for?

A. Google Kubernetes Environment
B. Google Kubernetes Engine
C. Google Container Engine
D. Google Compute Engine

**Answer: B — Google Kubernetes Engine**

---

### 2. GKE is primarily a managed service for:

A. Docker images
B. Kubernetes clusters
C. SQL databases
D. Virtual machines

**Answer: B — Kubernetes clusters**

---

### 3. Which component is responsible for running application Pods?

A. etcd
B. Scheduler
C. Worker/Data Plane nodes
D. API Server

**Answer: C — Worker/Data Plane nodes**

---

### 4. Which component stores Kubernetes cluster state?

A. kubelet
B. etcd
C. Scheduler
D. Service

**Answer: B — etcd**

---

### 5. Which component decides which node should run a Pod?

A. ReplicaSet
B. Scheduler
C. Service
D. kubelet

**Answer: B — Scheduler**

---

### 6. What is the smallest deployable unit in Kubernetes?

A. Container
B. Node
C. Pod
D. ReplicaSet

**Answer: C — Pod**

---

### 7. What is the primary purpose of a ReplicaSet?

A. Store cluster state
B. Expose Pods to the internet
C. Maintain the desired number of Pods
D. Select worker nodes

**Answer: C — Maintain the desired number of Pods**

---

### 8. What is the primary purpose of a Kubernetes Service?

A. Store container images
B. Provide stable networking to Pods
C. Create worker nodes
D. Schedule Pods

**Answer: B — Provide stable networking to Pods**

---

### 9. Which resource normally manages ReplicaSets?

A. Service
B. Deployment
C. Node
D. ConfigMap

**Answer: B — Deployment**

---

### 10. Which command lists GKE clusters?

A.

```bash
gcloud compute instances list
```

B.

```bash
gcloud container clusters list
```

C.

```bash
kubectl get clusters
```

D.

```bash
gcloud gke list
```

**Answer: B**

---

## Intermediate

### 11. Which command creates a GKE cluster?

A.

```bash
gcloud container clusters create my-cluster
```

B.

```bash
kubectl create cluster my-cluster
```

C.

```bash
gcloud compute clusters create my-cluster
```

D.

```bash
gke create my-cluster
```

**Answer: A**

---

### 12. After creating a GKE cluster, which command is commonly used to configure `kubectl` credentials?

A.

```bash
gcloud container clusters connect
```

B.

```bash
gcloud container clusters get-credentials
```

C.

```bash
kubectl auth login
```

D.

```bash
gcloud kubernetes login
```

**Answer: B**

---

### 13. What does this command do?

```bash
kubectl get pods
```

A. Creates Pods
B. Deletes Pods
C. Lists Pods
D. Restarts Pods

**Answer: C — Lists Pods**

---

### 14. What does this command show?

```bash
kubectl get nodes
```

A. Kubernetes Services
B. Worker nodes
C. Containers
D. Deployments

**Answer: B — Worker nodes**

---

### 15. You want to see more details about a Pod. Which command is most appropriate?

A.

```bash
kubectl describe pod <pod-name>
```

B.

```bash
kubectl details pod <pod-name>
```

C.

```bash
kubectl inspect <pod-name>
```

D.

```bash
kubectl show pod <pod-name>
```

**Answer: A**

---

### 16. Which command displays logs from a Pod?

A.

```bash
kubectl logs <pod-name>
```

B.

```bash
kubectl show-logs <pod-name>
```

C.

```bash
kubectl pod-logs <pod-name>
```

D.

```bash
gcloud logs pod <pod-name>
```

**Answer: A**

---

### 17. What does this command do?

```bash
kubectl get deployments
```

A. Lists Deployments
B. Creates a Deployment
C. Lists nodes
D. Lists Services

**Answer: A**

---

### 18. Which command exposes a Deployment as a Service?

A.

```bash
kubectl expose deployment my-app --type=LoadBalancer --port=80
```

B.

```bash
kubectl load deployment my-app
```

C.

```bash
kubectl service deployment my-app
```

D.

```bash
gcloud expose deployment my-app
```

**Answer: A**

---

### 19. What does `--type=LoadBalancer` generally request?

A. A ReplicaSet
B. A cloud-integrated external load-balancing service
C. A new worker node
D. A container image

**Answer: B**

---

### 20. Which command scales a Deployment to 5 replicas?

A.

```bash
kubectl scale deployment my-app --replicas=5
```

B.

```bash
kubectl replicas deployment my-app 5
```

C.

```bash
kubectl resize deployment my-app 5
```

D.

```bash
gcloud scale deployment my-app 5
```

**Answer: A**

---

## GKE Architecture

### 21. Which is the correct architecture?

A.

```text
Service → ReplicaSet → Scheduler → Container
```

B.

```text
Deployment → ReplicaSet → Pod → Container
```

C.

```text
Pod → Deployment → ReplicaSet → Node
```

D.

```text
Container → Pod → Deployment → Service
```

**Answer: B**

---

### 22. Which sequence correctly describes incoming application traffic?

A.

```text
User → etcd → Pod
```

B.

```text
User → Scheduler → Pod
```

C.

```text
User → Load Balancer/Ingress → Service → Pod
```

D.

```text
User → ReplicaSet → Worker Node
```

**Answer: C**

---

### 23. Which statement about ReplicaSets is correct?

A. They distribute network traffic.
B. They select worker nodes.
C. They maintain the desired number of Pods.
D. They store cluster state.

**Answer: C**

---

### 24. Which statement about worker nodes is correct?

A. They store Kubernetes state in etcd.
B. They run application workloads.
C. They decide Pod scheduling.
D. They manage Deployments.

**Answer: B**

---

### 25. Which component is the primary API entry point into Kubernetes?

A. Scheduler
B. etcd
C. API Server
D. kubelet

**Answer: C — API Server**

---

### 26. A Pod suddenly gets deleted. What Kubernetes mechanism helps recreate it when it is managed by a ReplicaSet?

A. Scheduler
B. ReplicaSet/controller reconciliation
C. Service
D. Load Balancer

**Answer: B**

---

### 27. What is the main difference between a Deployment and ReplicaSet?

A. Deployment manages application rollout and ReplicaSets maintain Pod replicas.

B. Deployment handles networking while ReplicaSet handles storage.

C. ReplicaSet manages nodes while Deployment manages containers.

D. There is no difference.

**Answer: A**

---

### 28. A Pod's IP changes after the Pod is recreated. Which Kubernetes abstraction prevents applications from needing to track individual Pod IPs?

A. Deployment
B. Service
C. ReplicaSet
D. Scheduler

**Answer: B — Service**

---

## GKE Standard vs Autopilot

### 29. Which GKE mode gives you more direct control over worker-node infrastructure?

A. Autopilot
B. Standard
C. Serverless
D. Managed SQL

**Answer: B — Standard**

---

### 30. Which GKE mode provides a more managed experience for the data plane?

A. Standard
B. Autopilot
C. Compute Engine
D. Cloud Run

**Answer: B — Autopilot**

---

### 31. Your team wants maximum control over node configuration and infrastructure. Which is generally more appropriate?

A. GKE Autopilot
B. GKE Standard
C. Cloud Functions
D. Cloud Storage

**Answer: B — GKE Standard**

---

### 32. Your team wants to minimize infrastructure/node-management responsibilities. Which would generally be more appropriate?

A. GKE Autopilot
B. Self-managed Kubernetes
C. GKE Standard
D. Compute Engine VMs

**Answer: A — GKE Autopilot**

---

# Advanced / Case Studies

### 33. Your Deployment specifies:

```yaml
replicas: 5
```

Currently only 4 matching Pods are running. What should Kubernetes attempt to do?

A. Delete one Pod
B. Create another Pod
C. Create another Service
D. Add another control plane

**Answer: B — Create another Pod**

---

### 34. A Pod is created but remains `Pending`. Which component should you investigate first for scheduling issues?

A. Service
B. Scheduler
C. ReplicaSet
D. Load Balancer

**Answer: B — Scheduler**

---

### 35. A Deployment has 3 healthy Pods, but users cannot reach the application through its Service. Which area should you investigate?

A. Only ReplicaSet
B. Service configuration/selectors and networking
C. etcd storage capacity only
D. Deployment replicas only

**Answer: B**

---

### 36. Your Service has:

```yaml
selector:
  app: backend
```

But your Pods have:

```yaml
labels:
  app: frontend
```

What is the likely result?

A. Service automatically changes the labels
B. Service won't select those Pods
C. ReplicaSet deletes the Pods
D. Scheduler moves the Pods

**Answer: B**

---

### 37. You have:

```text
Deployment
replicas = 3

Pod 1 → Node A
Pod 2 → Node B
Pod 3 → Node C
```

Node B fails. What is the expected Kubernetes behavior if capacity and configuration allow it?

A. Deployment permanently has only 2 replicas
B. ReplicaSet/controller causes a replacement Pod to be created, and the scheduler places it on an eligible node
C. Service creates a Pod
D. etcd creates a worker node

**Answer: B**

---

### 38. Production traffic suddenly increases. Your existing Pods are overloaded. Which Kubernetes capability is most directly relevant to automatically increasing Pod replicas?

A. HPA
B. etcd
C. kubelet
D. Ingress

**Answer: A — Horizontal Pod Autoscaler**

---

### 39. Your cluster needs more worker-node capacity because Pods cannot be scheduled due to insufficient resources. Which capability can automatically add nodes?

A. Horizontal Pod Autoscaler
B. Cluster Autoscaler
C. ReplicaSet
D. Service

**Answer: B — Cluster Autoscaler**

---

### 40. **Production Scenario — Advanced**

You deploy an application with:

```text
Deployment
   ↓
ReplicaSet
   ↓
3 Pods
   ↓
3 Worker Nodes
```

You expose it through a Service.

One Pod crashes, and simultaneously traffic increases.

Which combination best explains how Kubernetes can handle the situation?

A. Service creates the replacement Pod and etcd handles traffic.

B. ReplicaSet/controller maintains the desired replicas, Service routes traffic to available Pods, and HPA can increase replicas if configured.

C. Scheduler creates replicas and Deployment performs load balancing.

D. Worker nodes create Services automatically.

**Answer: B**

---

## 🔥 5 Questions You Should Be Able to Answer Without Thinking

**1. Who stores cluster state?**

> **etcd**

**2. Who decides where a Pod runs?**

> **Scheduler**

**3. Who maintains the number of Pods?**

> **ReplicaSet**

**4. Who provides stable access to Pods?**

> **Service**

**5. Who actually runs the Pods?**

> **Worker/Data Plane nodes**

### One-line architecture to memorize

```text
Deployment → ReplicaSet → Pods → Worker Nodes
                              ↑
                         Scheduler

Users → Load Balancer/Ingress → Service → Pods
```

And the control plane:

```text
kubectl → API Server → Controllers / Scheduler
                     ↕
                    etcd
```
