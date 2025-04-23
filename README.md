#  Setting Up Infrastructure on AWS Using Terraform

This project demonstrates how to automate the setup of cloud infrastructure on Amazon Web Services (AWS) using Terraform. It provides a comprehensive framework for deploying various AWS resources, including EC2 instances, S3 buckets, and VPC configurations, all defined through Infrastructure as Code (IaC).



##  Tools & Technologies

- **Terraform**
- **AWS**
- **AWS CLI**
- **Git**
- **VS Code / Any code editor**



##  What This Project Sets Up

- **VPC** (Virtual Private Cloud)
- **Public and Private Subnets**
- **Internet Gateway**
- **Route Tables**
- **NAT Gateway**
- **Security Groups**
- **EC2 Instances**
- **S3 Buckets**
- **IAM Roles & Policies**



##  Architecture Diagram

![Architectural Diagram](https://github.com/user-attachments/assets/ce61bc38-a0a4-489b-b703-a0ed81b27ff5)

> _This diagram shows the high-level AWS architecture deployed with Terraform._


##  Project Structure
```
terraform-aws-infrastructure/
├── modules/
│   ├── vpc/
│   ├── ec2/
│   └── s3/
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars
├── provider.tf
└── README.md


```

---

##  How to Deploy

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/terraform-aws-infrastructure.git
cd terraform-aws-infrastructure
```

### 2. Initialize Terraform
```bash
terraform init
```
### 3. Preview the Infrastructure Plan
```bash
terraform plan
```
### 4. Apply the Configuration
```bash
terraform apply
```
### Step 5: Access Your Application
Since the EC2 instances are in public subnets and traffic flows through a load balancer:

Terraform will print the URL:
load_balancer_dns_name = my-lb-1224074524.us-east-1.elb.amazonaws.com

OR Go to EC2 > Load Balancers in your AWS Console

Copy the DNS name of the Load Balancer 
https://my-app-lb-1224074524.us-east-1.elb.amazonaws.com

You can still check the public IP of the instances and access your application 
http://<your-public-ip>

<img width="908" alt="Project Result 2" src="https://github.com/user-attachments/assets/be212a5c-a23a-41a4-8da1-2b0b8b7848e5" />

<img width="906" alt="Project Result" src="https://github.com/user-attachments/assets/5ee34967-ad89-4d92-9d87-1d1a48bfce20" />

<img width="958" alt="Terraform Project Vscode Workspace" src="https://github.com/user-attachments/assets/4c15e6e1-e621-4a78-9236-340ca7dc6477" />

<img width="927" alt="Terraform Project, ALB Creation" src="https://github.com/user-attachments/assets/3a6fb9db-7531-4eb3-aeb4-2f7a1ba16e1a" />

<img width="913" alt="Terraform Project, Bucket Creation" src="https://github.com/user-attachments/assets/d43d14f9-b170-4905-8444-9a474fc6ccd0" />

<img width="916" alt="Terraform Project, EC2 Instance" src="https://github.com/user-attachments/assets/0a55054f-ea87-4445-b94a-fd6b9ad6ed85" />

<img width="929" alt="Terraform Project, TG Creation" src="https://github.com/user-attachments/assets/fda5ac06-eea8-4578-83e7-10a94a1f2481" />



### 6. Destroy Resources 
```bash
terraform destroy
```



