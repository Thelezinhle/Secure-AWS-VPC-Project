SECURE AWS VPC INFRASTRUCTURE DEPLOYMENT

PROJECT OVERVIEW
Implementation of a secure, tiered AWS VPC architecture with public and private subnets.

QUICK RESULTS
 VPC: 10.0.0.0/16 created
 Public Subnet: 10.0.10.0/24 (us-east-1a)
 Private Subnet: 10.0.1.0/24 (us-east-1a)
 Internet Gateway: Attached
 NAT Gateway: In Public Subnet
 Routing: Configured correctly
 Security: NACLs & Security Groups applied

ARCHITECTURE
See architecture-diagram.png for visual reference

KEY FEATURES
- Private instances can access internet via NAT Gateway
- Private instances cannot be reached directly from internet
- Tiered security with subnet isolation

SCREENSHOTS PREVIEW

VPC CIDR Configuration (01-vpc-cidr.png)
Subnets Deployment (02-subnets.png)
Internet Gateway Attached (03-igw-attached.png)
NAT Gateway Setup (04-nat-gateway.png)
Route Tables Configuration (05-route-tables.png)
EC2 Instances (06-ec2-instances.png)
NAT Routing Test (test1-nat-routing.png)
NAT Gateway Location (test2-nat-in-public.png)
Private Instance No Public IP (test3-no-public-ip.png)
Inbound Blocking Test (test4-inbound-blocked.png)

GETTING STARTED
See documentation.md for detailed technical specifications.

REQUIREMENTS MET
All project requirements satisfied with proper AWS VPC architecture.

CLEANUP
Remember to delete all resources to avoid charges.
