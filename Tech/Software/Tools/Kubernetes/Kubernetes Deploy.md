[[Kubernetes]] will follow similar steps as a [[CD Pipelines|CD Pipeline]] would normally do, but here are the extra steps it would take

- The pipeline applies a Kubernetes manifest (e.g., Deployment YAML) that specifies the new image tag.
    
- Kubernetes detects the change in the Deployment configuration.
    
- Kubernetes pulls the new container image from the registry.
    
- Kubernetes replaces old pods with new ones running the updated image, completing the rollout and ensuring its meeting the requirements.
