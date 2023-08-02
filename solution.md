# Solution

## Create a Firewall
1. Create a firewall in the Azure portal.
2. Assuming you have existing virtual network, make sure the firewall is created in the same region as the VN.
3. Create a public IP address for the firewall.

## Creeate a route table
1. Search for the Route Table service.
2. Create a route table to route all traffic from all ip address (0.0.0.0/0) to the private IP address of the firewall.
3. Then associate the route table to the vnet and default subnet.

## Configure Rule Collections for Firewall
1. Add a NAT rule that will route traffic from the firewall public IP to the private IP of a server over 3389 (RDP). This will translate the RDP connection from the public IP of the firewall to the server.
2. Add a network rule to allow UDP port 53 outbound to Google public DNS servers (8.8.8.8 and 8.8.4.4).
3. Configure an application rule collection to allow www.microsoft.com from the default subnet CIDR over the http and https protocols under Target FQDNs.

