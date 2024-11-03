# PacketDetective
A project to investigate Packets using Wireshark

This project is from Cyber Defenders.
So here's the breakdown of this project...🤓

In September 2020, your SOC detected suspicious activity from a user device, flagged by unusual SMB protocol usage. Initial analysis indicates a possible compromise of a privileged account and remote access tool usage by an attacker. 🐱‍💻
Your task is to examine network traffic in the provided PCAP files to identify key indicators of compromise (IOCs) and gain insights into the attacker’s methods, persistence tactics, and goals. Address the following questions to construct a timeline to better understand the progression of the attack. 🔍🕵️🔎

 

- Q1.	The attacker’s activity involved heavy SMB protocol usage, suggesting a significant data transfer or access pattern. Calculating the bandwidth SMB uses will help estimate the extent of file activity.
What is the amount of bandwidth, in bytes, used by the SMB protocol?

  - ANSWER:	I opened Wireshark and the captured file. Then, I went to Statistics and clicked on SMB. From there, I scrolled to the right and got the total number of Bytes as 4406.

    - ![PD1](https://github.com/user-attachments/assets/4b40c7d7-16c5-4f93-a7fe-5623a0c75318)
    - ![image](https://github.com/user-attachments/assets/d1bf9875-2f50-404d-9bf4-f6eaf77abeaa)

- Q2.	Authentication through SMB was a critical step in gaining access to the targeted system. Identifying the username used for this authentication will help determine if a privileged account was compromised.
Which username was utilized for authentication via SMB?

  - ANSWER:	The “Administrator” was compromised or the admin credentials were used. 

    - ![image](https://github.com/user-attachments/assets/9a95d5ca-78b5-43e1-b985-6436f277400d)

- Q3.	During the attack, the adversary accessed certain files. Identifying which files were accessed can reveal the attacker's intent.
What is the name of the file that was opened by the attacker?

  - ANSWER: eventlog

    - ![image](https://github.com/user-attachments/assets/f2987934-ff17-4e79-8872-edf2c6d62529)

- Q4.	Clearing event logs is a common tactic to hide malicious actions and evade detection. Pinpointing the timestamp of this action is essential for building a timeline of the attacker’s behavior.
What is the timestamp of the attempt to clear the event log? (24-hour UTC format)

  - ANSWER:	2020-09-23 16:50:16

    - ![image](https://github.com/user-attachments/assets/bb866e64-7b05-46b9-9ac8-9a5a16995ba2)

- Q5.	The attacker used "named pipes" for communication, suggesting they may have utilized Remote Procedure Calls (RPC) for lateral movement across the network. RPC allows one program to request services from another remotely, which could grant the attacker unauthorized access or control.
What is the name of the service that communicated using this named pipe?

  - ANSWER:	atsvc

    - ![image](https://github.com/user-attachments/assets/f7e0a992-fe92-4d77-b384-4d469273cdfa)

- Q6.	Measuring the duration of suspicious communication can reveal how long the attacker maintained unauthorized access, providing insights into the scope and persistence of the attack.
What was the duration of communication between the identified addresses 172.16.66.1 and 172.16.66.36?

  - ANSWER:	11.7247

    - ![image](https://github.com/user-attachments/assets/fcee0df3-1c90-4f1e-80a4-34dc75ea24f6)

- Q7.	The attacker used a non-standard username to set up requests, indicating an attempt to maintain covert access. Identifying this username is essential for understanding how persistence was established.
Which username was used to set up these potentially suspicious requests?

  - ANSWER:	backdoor

    - ![image](https://github.com/user-attachments/assets/5d1be858-9408-4f52-b647-6434b0555369)

- Q8.	The attacker leveraged a specific executable file to execute processes remotely on the compromised system. Recognizing this file name can assist in pinpointing the tools used in the attack.
What is the name of the executable file utilized to execute processes remotely?

  - ANSWER: PSEXESVC.exe

    - ![image](https://github.com/user-attachments/assets/dd8f3760-7231-4749-8aeb-4d658335bd9b)



This was a pretty cool project. I've learned that I need to do more projects with Wireshark to improve those skills, but overall, I would recommend this to everyone who is learning Cybersecurity but also Networking. I believe that it is important to understand this from a networking perspective, being that security is mostly based off of networking anyhow. It's an opportunity to strengthen your networking skills. 

