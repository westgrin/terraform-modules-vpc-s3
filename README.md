# Mini Project - Terraform Modules: VPC and S3 Bucket with Backend Storage (Local Setup)

## Project Overview
This project uses Terraform modules to provision an AWS VPC and S3 bucket, with an S3 backend for state storage in a WSL Ubuntu environment. It includes creating reusable modules, configuring an S3 backend with DynamoDB locking, and automating with GitHub Actions. Builds on previous Terraform projects (Jul 11-12, 2025).

## Setup
- Initiated on Jul 12, 2025, 12:45 PM WAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `C:\Users\Abraham\Documents\Workspace\terraform-modules-vpc-s3`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.

## Execution Steps
1. **Confirm Prerequisites**:
   - Verified AWS CLI with `aws --version`, `aws configure list`, and `aws sts get-caller-identity`.
   - Created S3 bucket and DynamoDB table for backend.
   - [Screenshot: `aws_prerequisites_output_local.png` - Shows AWS CLI verification.]
   - [Screenshot: `aws_backend_setup_output_local.png` - Shows S3 bucket and DynamoDB table.]
2. **Create VPC Module**:
   - Developed `modules/vpc/main.tf` for VPC, subnets, and internet gateway.
3. **Create S3 Module**:
   - Developed `modules/s3/main.tf` for S3 bucket with versioning and ACL.
4. **Configure Backend**:
   - Created `backend.tf` for S3 state storage with DynamoDB locking.
5. **Execute Script**:
   - Ran `terraform init`, `validate`, `plan`, and `apply`.
   - [Screenshot: `terraform_init_output_local.png` - Shows initialization.]
   - [Screenshot: `terraform_validate_output_local.png` - Shows validation.]
   - [Screenshot: `terraform_plan_output_local.png` - Shows plan output.]
   - [Screenshot: `terraform_apply_output_local.png` - Shows apply output.]
6. **Confirm Resources**:
   - Verified VPC and S3 bucket in AWS Console.
   - [Screenshot: `aws_vpc_output_local.png` - Shows VPC and subnets.]
   - [Screenshot: `aws_s3_output_local.png` - Shows S3 bucket.]
   - [Screenshot: `aws_backend_verify_output_local.png` - Shows Terraform state in S3.]
7. **Clean Up**:
   - Ran `terraform destroy` to remove resources.
   - [Screenshot: `terraform_destroy_output_local.png` - Shows destroy output.]
8. **Side Hustle Task**:
   - Automated deployment with GitHub Actions.
   - Pushed to `https://github.com/westgrin/terraform-modules-vpc-s3`.
   - [Screenshot: `github_actions_terraform_run_local.png` - Shows workflow run.]

## Learning Summary
This project advanced my Terraform skills by implementing modular configurations and S3 backend storage, building on my previous Terraform and Kubernetes projects (Jul 08-12, 2025). It reinforced infrastructure as code and automation with GitHub Actions, aligning with my DevOps goals (June 16, 2025).

## Tools Used
- **WSL Ubuntu Terminal**: For AWS CLI and Terraform commands.
- **VS Code**: For editing Terraform files and `README.md`.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For deployment automation.
- **Terraform**: For infrastructure as code.
- **AWS CLI**: For AWS authentication and backend setup.

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `aws_prerequisites_output_local.png`
  - `aws_backend_setup_output_local.png`
  - `terraform_init_output_local.png`
  - `terraform_validate_output_local.png`
  - `terraform_plan_output_local.png`
  - `terraform_apply_output_local.png`
  - `aws_vpc_output_local.png`
  - `aws_s3_output_local.png`
  - `aws_backend_verify_output_local.png`
  - `terraform_destroy_output_local.png`
  - `github_actions_terraform_run_local.png`
- **Script Link**: [GitHub Repository](https://github.com/westgrin/terraform-modules-vpc-s3)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/terraform-modules-vpc-s3.git`
2. Configure AWS CLI: `aws configure`
3. Create S3 bucket and DynamoDB table for backend.
4. Initialize Terraform: `terraform init`
5. Validate script: `terraform validate`
6. Plan execution: `terraform plan`
7. Apply configuration: `terraform apply`
8. Destroy resources: `terraform destroy`

## Troubleshooting
- Ensured valid S3 bucket and DynamoDB table for backend.
- Fixed AWS CLI authentication with `aws configure`.
- Set DNS to `8.8.8.8` for network issues.
- Verified system resources with `lscpu`, `free -h`, `df -h`.

## Conclusion
This project successfully automated VPC and S3 bucket creation with Terraform modules, configured an S3 backend, and implemented automation, enhancing my infrastructure as code skills for advanced DevOps scenarios.