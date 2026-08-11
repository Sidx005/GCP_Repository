Here are **short, exam-focused notes** from the uploaded App Engine transcript. 

# Google App Engine — Short Notes

### 1. What is App Engine?

* **Fully managed, serverless PaaS** for developing and hosting web applications.
* Google manages:

  * Servers
  * Infrastructure
  * Networking
  * Scaling
  * OS/runtime management
* Developer mainly focuses on **application code and data**.
* Suitable for **microservice-based architectures**.

### 2. PaaS

**Platform as a Service** means the cloud provider manages infrastructure such as:

```text
Runtime
Middleware
OS
Virtualization
Servers
Storage
Networking
```

You focus on:

```text
Application + Data
```

---

# 3. App Engine Environments

There are two:

| Standard                             | Flexible                       |
| ------------------------------------ | ------------------------------ |
| Runs in a secure sandbox             | Runs in Docker containers      |
| Pre-configured runtimes              | Custom runtimes supported      |
| Limited supported languages/versions | More languages/versions        |
| Can scale to **0**                   | Minimum **1** instance         |
| No SSH to underlying VM              | SSH capabilities available     |
| Limited third-party binaries         | Third-party binaries supported |
| Manual, Basic, Automatic scaling     | Manual, Automatic scaling      |
| Good for traffic spikes              | Good for consistent traffic    |

### Standard

Best when you need:

* Rapid scaling
* Sudden/extreme traffic spikes
* Scale-to-zero to reduce cost

### Flexible

Best when you need:

* Custom runtime
* Custom language/version
* Third-party binaries
* SSH access
* More control over the runtime

---

# 4. Scaling

### Standard supports:

```text
Manual
Basic
Automatic
```

### Flexible supports:

```text
Manual
Automatic
```

### Instance classes

**F classes:**

```text
F1, F2, F4...
```

→ Support **automatic scaling**

**B classes:**

```text
B1, B2, B4, B8...
```

→ Support **manual/basic scaling**, not automatic scaling.

### Scaling parameters

* **min_instances** → Minimum instances
* **max_instances** → Maximum instances
* **min_idle_instances** → Minimum warmed-up idle instances
* **max_idle_instances** → Maximum warmed-up idle instances

Idle instances help provide **faster scaling when traffic increases**.

---

# 5. App Engine Structure

Important hierarchy:

```text
GCP Project
   │
   └── App Engine Application (1 per project)
          │
          ├── Service 1
          │      ├── Version 1
          │      └── Version 2
          │
          └── Service 2
                 ├── Version 1
                 └── Version 2
```

Each version can run on **multiple instances**.

### Remember

> **One App Engine application per GCP project.**

---

# 6. Versions & Traffic

Deploying a new version creates a **new version**.

You can:

* Route 100% traffic to new version
* Roll back to previous version
* Split traffic between versions

Traffic can be split using:

* **IP address**
* **Cookie**
* **Random**

Example:

```text
Version 1 → 50%
Version 2 → 50%
```

Useful for **gradual deployments / canary-style deployments**.

---

# 7. `app.yaml`

`app.yaml` is the **deployment configuration file** for App Engine.

It can define things such as:

* Runtime
* Instance class
* Environment variables
* Handlers
* Scaling configuration

Example:

```yaml
runtime: nodejs16
instance_class: F2
```

If `instance_class` isn't specified, the default is **F1**.

---

# 8. Deployment

Typical command:

```bash
gcloud app deploy
```

App Engine uploads deployment files to a **Cloud Storage bucket** during deployment.

The deployed application is then served through the App Engine service URL.

---

# 9. App Engine Cleanup

Important exam point:

> **An App Engine application cannot be deleted once created.**

To stop charges, the transcript describes:

1. **Disable the App Engine application**
2. Delete the **App Engine default service account**
3. Delete App Engine-created **Cloud Storage buckets**

Even after disabling the application, storage resources can still incur charges.

---

# ⭐ Important Exam Points

Memorize these:

```text
App Engine = Managed PaaS / Serverless

Standard:
→ Sandbox
→ Preconfigured runtimes
→ Scale to 0
→ No underlying VM SSH
→ Manual + Basic + Automatic

Flexible:
→ Docker containers on Compute Engine VMs
→ Custom runtime
→ Minimum 1 instance
→ SSH available
→ Manual + Automatic

F class → Automatic scaling
B class → Manual/Basic scaling

1 App Engine application per project

Application
   ↓
Services
   ↓
Versions
   ↓
Instances

gcloud app deploy → Deploy application

app.yaml → Deployment configuration

Traffic → Can be migrated, rolled back, or split

App Engine application → Cannot be deleted; can be disabled
```



<img width="827" height="441" alt="image" src="https://github.com/user-attachments/assets/e478b47a-9748-4f97-bf43-365ed059711b" />


<img width="1058" height="641" alt="image" src="https://github.com/user-attachments/assets/6a2e1809-85ea-4621-86d2-8ad77b969f0d" />


<img width="966" height="599" alt="image" src="https://github.com/user-attachments/assets/9adf2c33-a672-4305-8801-949c0dafc5bf" />


<img width="930" height="510" alt="image" src="https://github.com/user-attachments/assets/d3aff953-7a37-4b23-b473-1b9aec1b2738" />


<img width="971" height="564" alt="image" src="https://github.com/user-attachments/assets/73366e37-8b1b-4e75-b78c-71e961630d5e" />


<img width="1145" height="443" alt="image" src="https://github.com/user-attachments/assets/21e1349e-7feb-4117-9a6f-550a85bdeda2" />


<img width="1055" height="471" alt="image" src="https://github.com/user-attachments/assets/51b6a364-26e3-4579-8e6d-4b0211a0994a" />

<img width="1059" height="468" alt="image" src="https://github.com/user-attachments/assets/15fd70b3-f377-4515-89fb-d9154da8a493" />

<img width="951" height="441" alt="image" src="https://github.com/user-attachments/assets/3d39315a-3c21-4139-9156-472679f9501c" />

<img width="949" height="548" alt="image" src="https://github.com/user-attachments/assets/4ab753c3-8e59-4048-87f0-179084564549" />
