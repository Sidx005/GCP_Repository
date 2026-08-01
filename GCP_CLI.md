# GCP CLI
Command: gcloud config list
```code
[accessibility]
screen_reader = True
[component_manager]
disable_update_check = True
[compute]
gce_metadata_read_timeout_sec = 30
[core]
account = siddharth.vishwanath@sigmoidanalytics.com
disable_usage_reporting = False
universe_domain = googleapis.com
[metrics]
environment = devshell
```


Command: gcloud auth list
```code
Credentialed Accounts

ACTIVE: *
ACCOUNT: siddharth.vishwanath@sigmoidanalytics.com

To set the active account, run:
    $ gcloud config set account `ACCOUNT`
```


### Gcloud IAM Commands
```bash
# Export a project ID variable
export PROJECT_ID=devops-iam-demo-<date>

# Create a new project via CLI
gcloud projects create $PROJECT_ID

# Set the active config to this project
gcloud config set project $PROJECT_ID

# Grant IAM role to a user (example: Viewer role)
gcloud projects add-iam-policy-binding $PROJECT_ID \
  --member="user:<email>" \
  --role="roles/viewer"

```
