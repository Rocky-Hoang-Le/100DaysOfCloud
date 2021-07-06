# Review on EC2, specifically placement groups

## Cloud Research

Today I reviewed all my knowledge on EC2 specifically on placement groups. Placement groups are logical partitions of EC2 for better communication, durability, and performance. The three types are Cluster, Partition, and Spread.

In a Cluster the EC2 partitions are packed together closely within an AZ allowing for low latency and high performance, and cannot be used in multi-az.

In a partition the instances are spread across the AZ and do not share underlying hardware. This is useful large distributed and replicated workloads.

In spread the instances are placed on different racks within the AZ which allows instances that should be separated  from each other to be separate. The spread can only be a max of 7 instances and can also be multi-az.

## Social Proof

[LinkedIn](https://www.linkedin.com/posts/rockyle98_100daysofcloud-100daysofaws-cloud-activity-6817996209983160320-fjM_)