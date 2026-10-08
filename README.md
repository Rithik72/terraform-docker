@"
# Task 3: Infrastructure as Code with Terraform

## Objective
Provision a local Docker container (nginx) using Terraform.

## Tools
- Terraform
- Docker Desktop
- Terraform Docker provider (kreuzwerker/docker)

## What I did
1. Wrote main.tf with a Docker provider, an nginx:latest image resource and a container resource mapping port 8080 to 80.
2. terraform init downloaded the Docker provider.
3. terraform plan previewed the changes (2 to add).
4. terraform apply created the image and container.
5. Verified with docker ps and by opening http://localhost:8080.
6. Inspected state with terraform state list and terraform state show.
7. terraform destroy removed everything.

## Files
- main.tf: Terraform configuration
- .terraform.lock.hcl: provider version lock
- logs/execution_log.txt: full execution log
- screenshots/nginx-welcome.png: nginx page served by the container

## Screenshot
![nginx welcome page](screenshots/task3nginx.png)

## What I learned
- IaC defines infrastructure in code that is repeatable and version-controlled.
- plan previews changes and apply executes them.
- The state file tracks the resources Terraform manages.
- The container depends on the image through docker_image.nginx.image_id (an implicit dependency).
- State files can hold sensitive data, so they are excluded with .gitignore.
"@ | Set-Content README.md
