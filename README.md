# Firewall-management

UFW-UFW stands for Uncomplicated Firewall.
It’s a user-friendly frontend for managing iptables, the default firewall system on many Linux distributions.

UFW is designed to simplify the process of configuring a firewall — making it easier for regular users to secure their systems.

Protects your system from unauthorized access.
Controls incoming and outgoing network traffic.
Helps secure servers (like web servers, SSH, databases, etc.).


To check the status of the UFW in our system we command "sudo ufw status"

Basically the status will be inactive and there are no pre rules configured.
<img width="1920" height="1042" alt="image" src="https://github.com/user-attachments/assets/70f19744-2b50-4ab1-9e04-6d73d2d973ca" />


So we here we are going to block the incoming traffic of the service Telnet which runs on port 23 and the command is 
"sudo ufw deny telnet" or "sudo ufw deny 23" 
we can also mention the specific protocl like TCP/UDP -- sudo ufw deny telnet/tcp
<img width="1920" height="1042" alt="image" src="https://github.com/user-attachments/assets/449c634f-1106-4a98-a707-8b402015b404" />


Now we are adding a rule to allow the traffic from SSH service which runns on port 22 the command is 
"sudo ufw allow ssh" same as telnet we can use port number protocol or service name .
<img width="1920" height="1042" alt="image" src="https://github.com/user-attachments/assets/5a705212-e601-4c40-84b2-c0e3e87029d6" />


Ok, Now we have configured the rules we want , now we need to start the firewall inorder to control the traffic.
sudo ufw enable -- starts the firewall
And then You can view the status and rules configured using the command -- sudo ufw status.
<img width="1920" height="1042" alt="image" src="https://github.com/user-attachments/assets/ef9d73b3-59e3-4031-abe3-62854c2f4b14"/>

If we want to reset the rules we can use the command -- sudo ufw reset
Which resets all the configured rules till now.


Working of the Firewall
1.Inspects each network packet ,Looks at the source IP, destination IP, port number, protocol, etc.
2.Matches the packet to rules, Rules define what traffic is allowed or denied (e.g., allow port 22)
3.Applies the action
If a rule matches: allow or block the traffic
If no rule matches: default to allow or deny (depending on the policy)
