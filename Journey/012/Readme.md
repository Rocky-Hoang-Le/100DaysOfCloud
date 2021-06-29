# Creating Bastion, Security groups, NACL, NAT Gateways, and VPC end points

## Introduction

Today I chose this topic because I learned about Bastion instances and wanted to implement it. I will be using the VPCs and other required stuff from yesterday for todays project. This project also introduces me to better security practices.

## Use Case

A Bastion is essentially a public facing EC2 instance that is used to communicate with a EC2 instance within a private subnet, and this is used for increased security. Security groups, NACL, NAT gateways, and VPC endpoints all serve to give the user more control over their network increasing security.

## Cloud Research

I learned more about Internet gateways and NAT gateways as well as what a Bastion is. Internet gateways allows EC2 instances that have public ip address within a VPC to receive inbound traffic from the internet while NAT gateways are for EC2 instances within a private subnet outbound access to the internet or other AWS resources.

NACL are firewalls that act at the subnet level and can deny and allow access for single ip address. Security groups are firewalls that act at the instance level and deny everything and can only have allow rules.

VPC endpoints allow for communication between instances and services within a vpc without having to go through the internet which can cause some vulnerabilites.

## Social Proof

✍️ Show that you shared your process on Twitter or LinkedIn

[LinkedIn](https://www.linkedin.com/posts/rockyle98_100daysofcloud-awscloud-aws-activity-6815456813769650176--qZF)
