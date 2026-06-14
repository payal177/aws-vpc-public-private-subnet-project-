# AWS VPC with Public and Private Subnets

## Project Overview

This project demonstrates the creation and configuration of a custom AWS Virtual Private Cloud (VPC) with public and private subnets. The project includes networking components such as an Internet Gateway, route tables, and an EC2 instance deployed in the public subnet.

## Architecture

<img width="175" height="292" alt="vpc-architecture" src="https://github.com/user-attachments/assets/3371f95c-f52f-46e0-802f-a6fa0a0cac0a" />


## Services Used

- Amazon VPC
- Amazon EC2
- Internet Gateway
- Route Tables
- Security Groups

## Architecture Details

| Component | Configuration |
|-----------|--------------|
| VPC | 10.0.0.0/16 |
| Public Subnet | 10.0.1.0/24 |
| Private Subnet | 10.0.2.0/24 |
| Internet Gateway | Attached to VPC |
| Route Table | Public Route Table |
| EC2 Instance | Amazon Linux 2023 |

## Steps Performed

1. Created a custom VPC with CIDR block `10.0.0.0/16`.
2. Created a public subnet (`10.0.1.0/24`).
3. Created a private subnet (`10.0.2.0/24`).
4. Attached an Internet Gateway to the VPC.
5. Configured route tables for internet access.
6. Associated the public subnet with the route table.
7. Enabled auto-assign public IPv4 address.
8. Launched an EC2 instance in the public subnet.
9. Installed and configured Apache HTTP Server.
10. Verified web server accessibility through the browser.

## Private Subnet Usage

The private subnet was created to simulate a production-ready architecture where backend services or databases can be deployed securely without direct internet access.

## User Data Script

```bash
#!/bin/bash
dnf update -y
dnf install httpd -y
systemctl start httpd
systemctl enable httpd

cat <<EOF > /var/www/html/index.html
<h1>AWS VPC with Public & Private Subnets</h1>
<p>Hosted on EC2 in a Public Subnet.</p>
EOF
```

## Screenshots

### VPC Created
<img width="1000" height="400" alt="VPC details page" src="https://github.com/user-attachments/assets/76426274-c684-4f2e-bf74-4c8456ac87f2" />

### Subnets
<img width="1000" height="200" alt="Public_Priavte_Subnets" src="https://github.com/user-attachments/assets/7e975bc7-0ed9-4ff7-a92d-9ccf938a24fe" />

### Internet Gateway
<img width="1000" height="200" alt="IG_to_VPC" src="https://github.com/user-attachments/assets/09271144-ea69-41d5-a0ff-f336fe11626e" />

### Route Table
<img width="1100" height="400" alt="RouteTable" src="https://github.com/user-attachments/assets/58788605-ade0-4d70-ba41-a1fc09f0bdae" />

### Route Association
<img width="1000" height="400" alt="RouteTableAssociation" src="https://github.com/user-attachments/assets/2bb8f913-7423-4f3f-b128-496858a006ce" />

### Security Group
<img width="1000" height="100" alt="Security-group" src="https://github.com/user-attachments/assets/f43b8a04-36f2-43a9-aa64-f9dbda63b5c4" />

### EC2 Instance
<img width="1000" height="400" alt="EC2_running" src="https://github.com/user-attachments/assets/06c63bef-bc5b-4b4d-8656-c64e771a9075" />


### Browser Output
<img width="1000" height="300" alt="Browser_Output" src="https://github.com/user-attachments/assets/8eef2015-b11b-4496-8949-3a7043cf6324" />

## Outcome

Successfully designed and implemented a custom AWS networking environment using VPC, public/private subnets, Internet Gateway, route tables, and EC2 deployment.
