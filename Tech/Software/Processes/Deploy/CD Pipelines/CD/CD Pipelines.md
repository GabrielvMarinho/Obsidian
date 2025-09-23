- You push code to the repo.
    
- The pipeline runs on a clean/empty [[Operating System]] to ensure consistency.
    
- The pipeline builds a new container image from the updated code.
    
- The image is stored in a container registry (e.g., Docker Hub, GitLab Registry, AWS ECR).
    
- The pipeline references this image for deployment.
    
- The image is deployed to a target environment.


In a QA and PRD environment it goes like this:

Any commit:
creates a new docker image
deploys to qa automatically
(deploys to prd manually, after testing the qa)
