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
load_balancer_dns_name = my-lb-123456.us-east-1.elb.amazonaws.com

OR Go to EC2 > Load Balancers in your AWS Console

Copy the DNS name of the Load Balancer 
https://my-app-lb-123456.us-east-1.elb.amazonaws.com

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

The project on "Terraform Automation on AWS Infrastructure" explains how the Infrastructure as a Code (IAC) tool, Terraform, can be used to create infrastructures on Amazon Web Services. Terraform allows you to manage infrastructure with configuration files rather than through a graphical user interface. It allows you to build, change, and manage your infrastructure in a safe,consistent, and repeatable way by defining your resource configurations that you can version and reuse. 

For this project to be successfully done, an AWS account must be created, with your IAM account being set up, a Terraform installed on your machine, and an AWS CLI installed. Access keys are created, which are a necessity for you to connect AWS with Terraform.

The above Architetcture of the project explains the services which will be created, There is VPC, a Custom Virtual Private Cloud to have the custom configuration for networking, which is housing two subnets, the VPC is also connected to internet gateway so that Internet connection can be passed, the Route Table to define that the Internet gateway sh0uld be connected to the subnet which will be attached to a Virtual Private Cloud(VPC), it defines where traffic goes to and how it flows to the subnet, Elastic Compute Cloud(EC2) instances would be created, then grant them IAM rules, they will be attached behind the Load Balancer, then give them S3 Access. I created a security group that I attached to the EC2 instances and the Application load balancer to control the traffic that is allowed to reach and leave the resources that it is associated with. Public subnets would be created which has a route to an internet gateway, allowing instances within the subnet to communicate with the internet. The map_ip_on_launch is set to true to specify that instances launched into the subnet should be assigned a Public IP address. Target groups are created that route requests to individual registered targets, such as EC2 instances, using the protocol and port number that you specify.  You can configure health checks on a per-target-group basis. Health checks are performed on all targets registered to a target group that is specified in a listener rule for your balancer. The Listener rules determine how the load balancer routes requests to the targets in one or more target groups. The target group and the Listener rule are both attached to the Application Load Balancer(ALB). For the Output, it is used to get some information printed on the terminal; for this, the Application Load Balancer's DNS name is printed to the terminal. 

NOTE: I created a Custom Virtual Private Cloud to have my custom configuration for networking. 

