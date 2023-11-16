# README
This Vagrantfile will do the following 

- Create a simple 3 node cluster using Ubuntu 20.04
- Each VM will have 4Gb RAM and2 CPUs
- Name each of the hosts to be mong-node01, mong-node02 and mong-node03
- Allocate IP addresses of 172.16.0.10, 172.16.0.20 and 172.16.0.30 to each of the nodes 
- Install MongoDB on each node and create a Replication Set 
- Edit /etc/hosts file on each VM for hostname/IP resolution
- Each VM will have 2 NIC (1 for NAT/external access and 1 for private network access)

## To run

`vagrant up`
or
`vagrant up node01` etc
