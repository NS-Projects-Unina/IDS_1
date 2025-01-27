"# IDS_1" 

Intrusion Detecting Project Summary
The project was designed to simulate the stages of a penetration test, using a victim, attacker, and detection system in a controlled environment, in this case of Virtual Machines. The goal was to simulate each step of an intrusion: Footprinting, Scanning, Enumeration, and Exploitation, while implementing and testing different intrusion detection techniques to monitor the activity.

Set-up
The setup involved configuring a network of 3 Virtual Machines using Oracle VirtualBox. The machines included the following roles:

•	Victim: A Metasploitable VM, which is vulnerable to exploitation. This VM was set up with default configurations for this intrusive pursopes.

•	Attacker: A Kali Linux VM, used as the attacker machine to perform various penetration testing activities. This included scanning, enumeration, and exploitation attempts.

•	Detection: Initially, an Ubuntu Server was configured to run Suricata, Wireshark (tshark in this case as it was a CLI), tcpdump… as an Intrusion Detection System (IDS). 

However, during the setup, multiple issues took place:
  
  o	The Ubuntu server had a network interface issue where the system used enp0s3 instead of the expected eth0. As a result, Suricata failed to detect the traffic properly, as the IDS was unable to listen on the correct network interface.
 
  o	Due to this issue, the planned detection system had to be changed for another Kali Linux VM configured to run this detection. This allowed Suricata to monitor traffic correctly.

To guarantee that all machines are in the same network the following command has to be executed:
sudo ifconfig eth0 192.168.1.xx netmask 255.255.255.0 up.
In my case victim is 10, attacker 20 and detection 30.
