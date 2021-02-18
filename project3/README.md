### Project Title - Deploy a high-availability web app using CloudFormation
This folder provides the starter code for the "ND9991 - C2- Infrastructure as Code - Deploy a high-availability web app using CloudFormation" project. This folder contains the following files:

### Files
#### network.yml
Cloudformation code for the network creation.
It has the following components:
- VPC
- PublicSubnet1
- PublicSubnet2
- PrivateSubnet1
- PrivateSubnet2
- InternetGateway
- InternetGatewayAttachment
- NatGateway1EIP
- NatGateway2EIP
- NatGateway1
- NatGateway2
- PublicRouteTable
- DefaultPublicRoute
- PublicSubnet1RouteTableAssociation
- PublicSubnet2RouteTableAssociation
- PrivateRouteTable1
- PrivateRouteTable2
- PrivateSubnet1RouteTableAssociation
- PrivateSubnet2RouteTableAssociation
- DefaultPrivateRoute2

There are some outputs that will be needed:
- VPC
- VPCPublicRouteTable
- VPCPrivateRouteTable1
- VPCPrivateRouteTable2
- PublicSubnets
- PrivateSubnets
- PublicSubnet1
- PublicSubnet2
- PrivateSubnet1
- PrivateSubnet2


#### network-parameters.json
This file contains the parameters needed for the network creation.
The parameters are:
- EnvironmentName
- CreatedBy
- VpcCIDR
- PublicSubnet1CIDR
- PublicSubnet2CIDR
- PrivateSubnet1CIDR
- PrivateSubnet2CIDR

#### servers.yml
Cloudformation code for the server side creation.
It has the following components:
- ProfileWithRolesForOurApp
- RoleForOurApp
- WebServerGroup
- LaunchConfig
- WebServerSecGroup
- WebServerScaleUpPolicy
- WebServerScaleDownPolicy
- CPUAlarmHigh
- CPUAlarmLow
- ApplicationLoadBalancer
- ALBListener
- ALBListenerRule
- ALBTargetGroup
- LBSecGroup

And there is one output needed, the ALB url
- URL

#### servers-parameters.json
This file contains the parameters needed for the network creation.
The parameters are:
- EnvironmentName
- CreatedBy
- KeyName
- S3BucketName
- FileName

### How to use it
There are 2 scripts created to help you.

#### ./create.sh
This script will create the stack in Cloudformation.
It needs 3 parameters:
- stack name
- template file
- parameter file

#### ./update.sh
This script will update an existing stack in Cloudformation.
It needs 3 parameters:
- stack name
- template file
- parameter file
