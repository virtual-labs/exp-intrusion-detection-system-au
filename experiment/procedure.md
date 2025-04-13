### Procedure

1. In this experiment, you will learn how to configure a firewall to block traffic from specific IP address that is sending malicious packets to a server.

2. Enter the configuration mode of the firewall by typing the following command:
    - configure terminal

3. Get the interface information of the server which is in interface. Try to find the IP address of the server using the following command:
    - show interface INTERFACE_NAME

4. Access lists are a set of rules that are used to filter traffic. They are used to control the traffic that is allowed to pass through a router or a firewall. Access lists are used to filter traffic based on the source and destination IP addresses, source and destination ports, and protocol type. In this experiment, you will be using access lists to block traffic from specific ports from a server to a client.

5. Get the access list information of the firewall using the following command:
    - show access-lists

6. Access lists are a set of rules that are used to filter traffic. Modify the access list to block and allow traffic from specific ports from a server to a client. Towards the right side of this experiment you will see a list of packets. The packets are sent from a client to a server. The packets hold an IP address and it's packet content. Click on the packet to view the complete packet content and decide which packets to block and allow based on the packet content. Malicious packets usually hold SQL Injection code or XSS scripts or Bash Scripts. You can block these packets by blocking the IP Address from which the packets are sent. Use the below commands to do so.

Use the following command to block traffic of tcp packets from a specific Client IP Address to the server:
    - access-list block-packet deny tcp CLIENT_IP_ADDRESS host SERVER_IP_ADDRESS

7. Use the following command to allow traffic of tcp packets from a specific port to the server:
    - access-list allow-packet allow tcp CLIENT_IP_ADDRESS host SERVER_IP_ADDRESS

8. Note that we are only dealing with tcp packets in this experiment. Hence, tcp is always used in the above commands. In the commands, allow-packet and block-packet are the names of the access lists that you want to modify, these are existing access lists, creation of new access-list is restricted for this experiment. The SERVER_IP_ADDRESS is the IP address of the server and the CLIENT_IP_ADDRESS is the client IP address from which you want to block traffic, refer to the packet list to find the IP address numbers and the output of the second step to find the IP address of the server.
