TECHNICAL DOCUMENTATION

AWS RESOURCE DETAILS

VPC
ID: vpc-035686006b832dbfb
CIDR: 10.0.0.0/16
Region: us-east-1
DNS: Enabled

SUBNETS

Public-Subnet
ID: subnet-0dc6291ad855a0e28
CIDR: 10.0.10.0/24
AZ: us-east-1a

Private-Subnet
ID: subnet-0532f6fd02d3f315f
CIDR: 10.0.1.0/24
AZ: us-east-1a

INTERNET GATEWAY
ID: igw-0005c508ed50aa709
Name: Project-IGW
Status: Attached

NAT GATEWAY
ID: nat-061d21077f33ac006
Name: Project-NAT-Gateway
Subnet: Public-Subnet
Status: Available
Public IP: 10.0.10.15

ROUTE TABLES

Public-Route-Table (rtb-0f7dd4710251b2856)
Route: 0.0.0.0/0  igw-0005c508ed50aa709
Association: Public-Subnet

Private-Route-Table (rtb-0f94e3db4cb8b5705)
Route: 0.0.0.0/0  nat-061d21077f33ac006
Association: Private-Subnet

EC2 INSTANCES

Bastion-Host (i-0e22ce08d203e3af8)
Public IP: 44.193.201.218
Private IP: 10.0.10.78
Subnet: Public-Subnet
Type: t2.micro

Private-Instance (i-0aba945f8628baa30)
Public IP: None
Private IP: 10.0.1.251
Subnet: Private-Subnet
Type: t2.micro

SECURITY
Network ACLs: Default applied
Security Groups: Bastion-SG, default

TESTING EVIDENCE

Screenshot Index
1. 01-vpc-cidr.png - VPC with 10.0.0.0/16
2. 02-subnets.png - Both subnets in us-east-1a
3. 03-igw-attached.png - Internet Gateway attached
4. 04-nat-gateway.png - NAT Gateway in Public Subnet
5. 05-route-tables.png - Route table configurations
6. 06-ec2-instances.png - EC2 instances (Bastion with IP, Private without)
7. test1-nat-routing.png - Private route to NAT Gateway
8. test2-nat-in-public.png - NAT Gateway in Public Subnet
9. test3-no-public-ip.png - Private instance has no public IP
10. test4-inbound-blocked.png - Ping timeout to private instance

COMPLIANCE MATRIX

Requirement: VPC 10.0.0.0/16
Status: COMPLETE
Proof: 01-vpc-cidr.png

Requirement: Subnets in same AZ
Status: COMPLETE
Proof: 02-subnets.png

Requirement: IGW attached
Status: COMPLETE
Proof: 03-igw-attached.png

Requirement: NAT in Public Subnet
Status: COMPLETE
Proof: 04-nat-gateway.png

Requirement: Private routes via NAT
Status: COMPLETE
Proof: test1-nat-routing.png

Requirement: Public routes via IGW
Status: COMPLETE
Proof: 05-route-tables.png

Requirement: NACLs applied
Status: COMPLETE
Proof: Default NACLs

Requirement: No public IP on private
Status: COMPLETE
Proof: test3-no-public-ip.png

COST INFORMATION
EC2 Instances: t2.micro (Free Tier)
NAT Gateway: Approximately 0.045 per hour
Total Estimated: Less than 2.00
Cleanup Required: Yes
