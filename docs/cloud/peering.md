---
sidebar_postion: 3
title: Peering Connections
--- 



# Peering Connections

Peering connections are used  to connect a Dragonfly Cloud private network with a VPC in your cloud account to establish communication between the two networks over private ip space.

Private IP space communication is more secure, performant and reduces data transfer costs incurred by cloud providers.


Once you created a private network as described in [Networks](./networks) click the network three dots menu and click +Connection 


Continue to [AWS](#aws) or [GCP](#gcp) based on your cloud provider.


## AWS
Specify the region, CIDR, account ID (also called owner ID in AWS) and VPC ID of your AWS VPC from where you want to connect and click Create.

The connection will be created in an inactive state.

Accept the peering connection in your AWS account console 
Create a route in your AWS VPC, set the destination to the CIDR of the dragonfly cloud private network, set the target to the AWS peering connection id.
More information about AWS peering connection here 

At this point you should see the connection in state active in the dragonfly cloud console.

If you haven’t done so already, create a data store with a private endpoint.


##  GCP
Specify the CIDR, GCP project ID and VPC ID of your GCP VPC from where you want to connect and click Create.

The connection will be created in an inactive state. Follow the google cloud guide <a href="https://cloud.google.com/sdk/gcloud/reference/compute/networks/peerings/create">here</a> , specify `–peer-network` and `–peer-projec`t with the account ID and VPC ID values from the dragonfly cloud private network you wish to connect. Observe the connection becomes active after a few moments      

If you haven’t done so already, create a data store with a private endpoint.

