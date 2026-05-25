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
- VirtualBox (1 Wazuh server, 1 Wazuh agent)

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*

Step 1: Create a virtualized Wazuh server


