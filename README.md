# Wazuh SIEM + Suricata IDS

## Objective
[Brief Objective - Remove this afterwards]

To gain hands-on experience on SIEM (Security Information and Event Management)  and IDS (Intrusion Detection System), I created a virtualized environment and used Wazuh, a popular open-source SIEM and XDR, and Suricata, an open-source IDS. The goal was to learn how these systems are implemented, set-up, used, and viewed in a real-world scenario; To further what I know to something I can apply.

After the succesful implementation, a basic attack is simulated to ensure everything is captured properly; This helps me better understand how a potentil attack will be viewed in real-time.

The next part of this project would be to have a seperate didcated SIEM server with Suricata IDS connected directly to the default gateway (or any network vantage point) via TAP or SPAN port. The goal is to capture ALL network traffic, instead of only the singular host.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]


- SIEM: Wazuh
- IDS: Suricata
- VirtualBox, Type 2 Hypervisor (1 Wazuh server, 1 Wazuh agent)
    Both will be using Ubuntu for compatibility.

I also referred to the Wazuh documentation to help guide the installation and proper configuration, so that will be mentioned many times.

<img width="2552" height="1383" alt="Screenshot 2026-05-25 065739" src="https://github.com/user-attachments/assets/967c9e2f-2217-4eef-8849-7f04d06b5c0a" />

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*

Step 1: Create a VM for the Wazuh Server

Open VirtualBox, select "New" to create a new VM. Then select the Ubuntu ISO image to create the VM with Ubuntu installed.

In terms of resource allocation, refer to the Wazuh documentaions. Under "Quickstart," it tells you a standard requirement for the Wazuh server to run + OS compatibilities.

<img width="2542" height="1372" alt="Screenshot 2026-05-25 065944" src="https://github.com/user-attachments/assets/2c4d285d-6187-4600-ad64-1c3295668517" />

For homelab purposes, I allocated the minimum recommended: 4 Processors, 8 GB of RAM, and 50 GB storage.

Follow through with the VM creation, Ubuntu install, and the VM should be ready.


Step 2: Install Wazuh Server

I downloaded via assissted installation:
```
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh && sudo bash ./wazuh-installation.sh -a
```
Now the Wazuh Server is successfully installed and an admin login (username and password) is given.

To login and access the Wazuh dashboard, copy the host IP address and paste it onto a web browser search engine. Here is where you'd use the given admin credentials.

Step 4: Explore the Dashboard

While this isn't an actual step important to completing this lab, it is important to look around and familiarize myself with the SIEM dashboard.

Currently, there is no agent deployed, so the SIEM isn't displaying any information at all.

The next few steps is deploying the Wazuh Agent, so that we can start seeing logs being generated on the SIEM.


Step 3: Create a VM for the Wazuh Agent

Using the same process as Step 1, I created a new host to serve as my Wazuh Agent.

Less resources is allocated, as this is just a client: 2 Processors, 4 GB of RAM, and 30 GB storage.

From here on out, both VMs (Wazuh Server and Agent) will be on and active. This is generally important to keep in mind as while both are on, it is using my PC's resources and, in effect, can impact my overall PC performance; This is also why following the recommended resource allocation is important, so we can balance out server performance without detrementing our overall device.

If my device was to ONLY serve as a Wazuh Server, allocating more resources would be best to increase it's performance. I could use a Type 1 Hypervisor with a "bare metal" approach to grant us direct access to hardware resources.


Step 4: Deploy Wazuh Agent into Wazuh Server

