# 🏠 Homelab
![Project Status](https://img.shields.io/badge/status-in%20development-orange)  

## **Objective**
This cybersecurity homelab is designed to replicate real-world enterprise network environments, conduct security testing, and practice threat detection, incident response, and vulnerability management. The architecture follows a typical attack chain, simulating various security scenarios.

## **Hardware Setup**

### **Hardware Utilization Breakdown**
| **Hardware** | **Role** | **Purpose** |
|-------------|---------|------------|
| **Beelink Mini PC (32GB RAM, 1TB SSD)** | **Virtual Enviornment Host** | Runs VMs for target machines (Windows, Linux, vulnerable hosts). |
| **ZimaBlade (16GB RAM, 20TB SSD)** | **NAS Storage** | Provides centralized NAS for VM disk storage, backups, and logs. |
| **Razer Blade 15 (32GB RAM, 1TB SSD, Parrot OS)** | **Attack Machine** | Runs Parrot OS, penetration testing tools, and attack simulations. |
| **Beelink Mini PC (32GB RAM, 1TB SSD)** | **Security Server** | Hosts Wazuh SIEM, EDR, and vulnerability scanning tools. |
| **Jetson Nano (4GB RAM, 128GB SSD)** | **Local AI** | Clustered with Mini PCs, integrates with all Proxmox-hosted VMs and security server for AI-driven threat detection, automation, and real-time attack analysis. |

## **Network Architecture Overview**
[Infrastructure.png](https://postimg.cc/bsB7sfY3)

1. **Email Server (SMTP)** → Entry point for phishing and reconnaissance.
2. **Hypervisor** → Hosts virtual machines to replicate enterprise systems.
3. **Directory Services Server** → Represents Active Directory for user authentication, privilege escalation, and persistence testing.
4. **Security Server** → Centralized security monitoring with SIEM, EDR, and vulnerability scanning.
5. **Workstations**:
   - **Local AI Workstation** → Simulates a user machine, attack target.
   - **Enterprise Workstation** → For lateral movement testing.
   - **Security Workstation** → For defensive security operations.

## **Software Stack**

<table>
    <tr>
        <th>Logo</th>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><img width="32" src="https://imgs.search.brave.com/I3zuH4XrMirJ_2EsXmJpKDjPnk_iNORLotYT0xQgqsA/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9zZWN1/cml0eS50cnVlbmFz/LmNvbS9pbWFnZXMv/TG9nb1RydWVOQVNT/Y2FsZS5wbmc"></td>
        <td><a href="https://www.truenas.com/truenas-scale/">TrueNAS Scale</a></td>
        <td>Hypervisor for centralized storage, VM hosting, and backup management within my homelab infrastructure.</td>
    </tr>
</table>

### **Hypervisor & Virtualization**
   - **VMware Workstation** (on Zimablade) – Virtual machine management.
   - **TrueNAS Scale** (on Synology NAS) – Storage solution for logs, backups, and VM storage.

### **Active Directory & Domain Services**
   - **Ubuntu Server 24 (Directory Services Server)**
   - **Domain Controller, DHCP, DNS, Group Policy Objects (GPO)**.

<table>
    <tr>
        <th>Logo</th>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><img width="32" src="https://www.svgrepo.com/download/499807/home-page.svg"></td>
        <td><a href="https://github.com/gethomepage/homepage">Homepage</a></td>
        <td>My customized portal to my homelab & internet</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/n8n.svg"></td>
        <td><a href="https://n8n.io/">n8n</a></td>
        <td>Secure, AI-native workflow automation</td>
    </tr>
</table>

### **Security Tools & Monitoring**
   - **Wazuh SIEM** (on Beelink Mini PC) – Logs, threat detection, and monitoring.
   - **Elastic Stack (ELK)** – Visualization and log aggregation.
   - **Suricata / Zeek** – Network intrusion detection and analysis.
   - **Sysmon + Windows Event Logging** – Endpoint monitoring.

### **Vulnerability & Exploitation**
   - **Nessus / OpenVAS** – Vulnerability scanning.
   - **Metasploit Framework** – Penetration testing and exploitation.
   - **BloodHound / SharpHound** – Active Directory attack path analysis.

<table>
    <tr>
        <th>Logo</th>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><img width="32" src="https://www.svgrepo.com/download/499807/home-page.svg"></td>
        <td><a href="https://github.com/gethomepage/homepage">Homepage</a></td>
        <td>My customized portal to my homelab & internet</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/n8n.svg"></td>
        <td><a href="https://n8n.io/">n8n</a></td>
        <td>Secure, AI-native workflow automation</td>
    </tr>
</table>

### **Attack & Defense Simulation**
   - **Atomic Red Team** (on Razer Blade running Parrot OS) – Adversary emulation testing.
   - **C2 Frameworks** – Cobalt Strike, Sliver, or Mythic for Red Team exercises.
   - **Windows & Linux Workstations** – For attack testing, phishing simulations, and lateral movement.

## **Implementation Plan**

### **1. Network & Virtual Machine Deployment**
- Set up **VMware Workstation** on the Zimablade.
- Create virtual subnets for **internal enterprise, DMZ, and security zones**.
- Deploy a **Ubuntu Server VM** for **Active Directory**.
- Deploy a **Linux TalosOS VM** for **Wazuh SIEM and ELK Stack**.

### **2. Security Monitoring & Logging**
- Configure **Wazuh SIEM** to collect logs from Windows and Linux machines.
- Enable **Sysmon and Windows Event Logging** for endpoint monitoring.
- Integrate **Suricata/Zeek** for network intrusion detection.

### **3. Vulnerability Assessment**
- Deploy **Nessus/OpenVAS** for internal vulnerability scanning.
- Conduct Active Directory enumeration with **BloodHound/SharpHound**.

### **4. Attack Simulation & Incident Response**
- Conduct **phishing simulations** via the SMTP server.
- Perform **privilege escalation techniques** on the AD server.
- Execute **lateral movement techniques** to mimic real-world attacks.
- Use **SIEM and EDR logs** to analyze and respond to threats.

## **Workflow Example: Attack Chain Simulation**
1. **Initial Access**: Phishing attack via SMTP server.
2. **Reconnaissance**: Enumerate users and services on the AD server.
3. **Privilege Escalation**: Exploit misconfigured AD settings.
4. **Lateral Movement**: Move from Local AI Workstation → Enterprise Workstation.
5. **Persistence**: Deploy scheduled tasks, registry modifications.
6. **Exfiltration**: Extract data from Directory Services.

## Networking

I use a Unifi Express Router, configured with 7 different VLANs which are all locked down by strict traffic rules.

I use [Cilium](https://cilium.io/) as my CNI. I use LoadBalancer IPAM to assign IP addresses to my LoadBalancer services and use Cilium as an ingress controller. This way, I don't need to install and maintain a seperate ingress controller like Traefik, which I used in the past.

### Storage

I use a Synology DS224+ as a NAS. I use the Synology CSI driver to provision Persistent Volumes from my clusters directly on the NAS. I also have an NFS share for data that needs to be shared between clusters.

## Secret Management

Azure Key Vaults are used to store my secrets. I sync them to my cluster using the External Secrets Operator.
