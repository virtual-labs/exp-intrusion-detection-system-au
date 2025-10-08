
1. In this experiment, you will learn how to configure a firewall to block malicious traffic from a specific IP address.

2. Enter the firewall's configuration mode:
    - `configure terminal`

3. Find the IP address of the server, which you'll need for the firewall rules. Replace `INTERFACE_NAME` with the correct interface name.
    - `show interface INTERFACE_NAME`

4. You will be using access lists to filter traffic. Access lists are rule sets that control traffic based on details like IP addresses and ports. View the existing access lists with:
    - `show access-lists`

5. To the right, you'll see a list of incoming TCP packets. Examine them for malicious content (e.g., SQL injection, XSS, or scripts). Your task is to block packets from malicious IP addresses.

6. Use the following commands to modify the `allow-packet` and `block-packet` access lists. In these commands:
    - `CLIENT_IP_ADDRESS` is the source IP from the packet list.
    - `SERVER_IP_ADDRESS` is the destination IP you found in step 3.

    Use this command to **block** a malicious client:
    - `access-list block-packet deny tcp CLIENT_IP_ADDRESS host SERVER_IP_ADDRESS`

    Use this command to **allow** a client:
    - `access-list allow-packet allow tcp CLIENT_IP_ADDRESS host SERVER_IP_ADDRESS`

7. **Note**: This experiment only deals with TCP packets and modifying existing access lists. You do not need to create new ones.
