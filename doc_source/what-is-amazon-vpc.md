# What is Amazon VPC?<a name="what-is-amazon-vpc"></a>

* Amazon Virtual Private Cloud \(Amazon VPC\)
  * -- enables you to -- launch AWS resources | virtual network / you've defined
    * virtual network == (closely) traditional network | your own data center + benefits of using scalable infrastructure of AWS
  * == 👀1 subnet / EACH Availability Zones | Region + EC2 instances | EACH subnet + internet gateway👀

![\[A VPC with an internet gateway and subnets in three Availability Zones.\]](http://docs.aws.amazon.com/vpc/latest/userguide/images/how-it-works.png)

## Features<a name="amazon-vpc-features"></a>

* allows
  * configuring a VPC / provide the connectivity / your applications need

**Virtual private clouds \(VPC\)**  
* [VPC](configure-your-vpc.md)
  * once you create a VPC -> you can add subnets

**Subnets**  
* [subnet](configure-subnets.md)
  * == range of IP addresses | your VPC
  * 👀must reside | 1! Availability Zone 👀
  * once you add subnets -> you can deploy AWS resources | your VPC

**IP addressing**  
* [IP addresses](vpc-ip-addressing.md) / you -- can assign to -- 
  * your VPCs and subnets
    * IPv4
    * IPv6
  * your VPC, such as EC2 instances, NAT gateways, and Network Load Balancers
    * public IPv4
    * IPv6 GUA addresses 

**Routing**  
* [route tables](VPC_Route_Tables.md)
  * allows
    * determining where network traffic / from your subnet or gateway -- is -- directed

**Gateways and endpoints**  
* [gateway](extend-intro.md)
  * connects your VPC -- to -> ANOTHER network
    * _Example1:_ [internet gateway](VPC_Internet_Gateway.md) to connect your VPC -- to the -- internet
    * 👀if you want to connect to AWS services privately / NO use an internet gateway or NAT device -> use a [VPC endpoint](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-access-aws-services.html) 👀

**Peering connections**  
* see [VPC peering connection](https://docs.aws.amazon.com/vpc/latest/peering/)
* uses
  * route traffic between the VPC1's resource -- & -- VPC2's resource

**Traffic Mirroring**  
* see [Copy network traffic](https://docs.aws.amazon.com/vpc/latest/mirroring/)
* -- from -- network interfaces
* uses
  * -- send it to -- security & monitoring appliances
    * Reason: 🧠 deep packet inspection 🧠

**Transit gateways**  
* see [transit gateway](extend-tgw.md)
* uses
  * central hub / -- route traffic between -- your
    * VPCs,
    * VPN connections
    * AWS Direct Connect connections

**VPC Flow Logs**  
* see [flow log](flow-logs.md)
* allows
  * capturing information -- about the -- IP traffic / going to and from network interfaces | your VPC

**VPN connections**  
* see [AWS Virtual Private Network \(AWS VPN\)](vpn-connections.md)
* uses
  * connect your VPCs -- to your -- on\-premises networks 

## Getting started with Amazon VPC<a name="getting-started"></a>

* 👀[default VPC](default-vpc.md) / EACH AWS Region 👀
  * configured / you can immediately start, about EC2 instances 
    * launching
    * connecting
  * see [Get started with Amazon VPC](vpc-getting-started.md)
* see [Create a VPC](create-vpc.md)

## Working with Amazon VPC<a name="VPCInterfaces"></a>

* ways to manage your VPCs:
  + **AWS Management Console**
  + **AWS CLI**
    + see [AWS Command Line Interface](https://aws.amazon.com/cli/)
  + **AWS SDKs**
    + see [AWS SDKs](http://aws.amazon.com/tools/#SDKs)
  + **Query API**
    + == low\-level API actions / you call -- via -- HTTPS requests
    + 👀MOST direct way -- to access -- Amazon VPC👀
    + requirements
      + your application handle low-level details
        + _Example1:_ generating the hash -- to sign -- the request
        + _Example2:_ error handling
    + see [Amazon VPC actions](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/OperationList-query-vpc.html)

## Pricing for Amazon VPC<a name="pricing"></a>

* 👀if you use VPC -> NO additional charges 👀
* if you use VPC components -> charges
  * _Example of these VPC components:
    * NAT gateways,
    * IP Address Manager,
    * traffic mirroring,
    * Reachability Analyzer,
    * Network Access Analyzer
* see [Amazon VPC Pricing](http://aws.amazon.com/vpc/pricing/)