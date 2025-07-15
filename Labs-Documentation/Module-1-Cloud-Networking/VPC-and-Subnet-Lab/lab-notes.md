#  VPC and Subnet Creation Lab

##  Date
July 14, 2025

## Objective
To create a custom Virtual Private Cloud (VPC) with public and private subnets, attach an Internet Gateway, and configure a route table for internet access.

## Services Used
- AWS VPC  
- Subnets  
- Internet Gateway  
- Route Table  
- EC2 (optional)

##  Steps Taken

1. **Create a Custom VPC**
   - Name: `uyicloud-vpc`
   - CIDR: `10.0.0.0/16`

2. **Create Public Subnet**
   - Name: `public-subnet`
   - CIDR: `10.0.1.0/24`
   - Enable Auto-assign public IP

3. **Create Private Subnet**
   - Name: `private-subnet`
   - CIDR: `10.0.2.0/24`
   - Auto-assign public IP: disabled

4. **Create Internet Gateway**
   - Name: `uyicloud-igw`
   - Attach to `uyicloud-vpc`

5. **Create Route Table**
   - Name: `public-rt`
   - Associate with `public-subnet`
   - Add route: `0.0.0.0/0` → Internet Gateway

6. (Optional) **Launch an EC2 Instance**
   - In `public-subnet`
   - Attach Elastic IP

7. **Test SSH and internet access**

##  Screenshots
- `vpc-diagram.png` (add your diagram here)
- `instance-ssh.png` (optional)

## Challenges
- SSH: Permission denied → Fixed with `chmod 400 mykey.pem`
- Route table not working initially → Rechecked association

## What I Learned
- How to create a VPC with subnets in AWS
- How route tables control traffic flow
- Importance of correct associations in networking
