# 🏠 AI Cybersecurity Homelab
![Project Status](https://img.shields.io/badge/status-in%20development-orange)  

A comprehensive cybersecurity homelab integrating red team and blue team capabilities with modern AI technologies for continuous security testing, monitoring, and improvement.

## 💻 Overview

This homelab demonstrates how open-source AI models can be integrated with traditional security tools to create a self-improving, automated cybersecurity testing and monitoring environment. The system continuously monitors for threats, analyzes security data, and learns from both attacks and defensive measures.

### 💼 Key Features

- **AI-Powered Analysis**: Local AI models for security data analysis without cloud dependencies
- **Automated Reconnaissance**: AI-driven reconnaissance and vulnerability scanning
- **Threat Intelligence**: Integrated threat intelligence platform with OpenCTI
- **Security Monitoring**: Real-time monitoring with Wazuh SIEM
- **Automation & Orchestration**: Workflow automation with n8n
- **Attack Simulation**: Automated and semi-automated attack scenarios
- **Documentation**: Comprehensive documentation and reporting

## 🏗️ Hardware Setup

- **Hypervisor**: Mini PC with AMD Ryzen 5, 64GB DDR4 RAM, 1TB NVME running Proxmox
- **Attack Machine**: Razer Blade 15 with Intel i7, 32GB RAM, 1TB NVME running Parrot OS
- **Storage**: 20TB Synology NAS configured as ZFS pool in TrueNAS

## 🌐 Network Architecture

The homelab is segmented into three primary networks:
- **Management Network** (192.168.0.0/24): For administration and control
- **Attack Network** (192.168.10.0/24): For red team operations
- **Defense Network** (192.168.20.0/24): For blue team operations and target systems

## 🔗 Core Components

### 🤖 AI Integration

- **Ollama**: Local AI model serving with models like Llama3, Falcon, and Gemma
- **AI Agent Framework**: Custom Python framework for security-focused AI operations
- **Multi-Party Computation**: Secure computation for sensitive operations

### 💙 Blue Team Components

- **Wazuh SIEM**: Security monitoring, log analysis, and alerting
- **OpenCTI**: Threat intelligence platform for indicator management and analysis
- **n8n Blue Team Workflows**: Automated security monitoring and incident response

### 👾 Red Team Components

- **Parrot OS Toolkit**: Full suite of security testing tools
- **n8n Red Team Workflows**: Automated reconnaissance and attack simulation
- **Shodan Integration**: External reconnaissance and attack surface analysis

### 🎯 Target Environment

- **Vulnerable Web Server**: Web application testing environment
- **Vulnerable Database Server**: Database security testing environment
- **Windows Server**: Active Directory and Windows service testing

## 📝 Setup Instructions

The complete setup instructions are available in the `documentation` directory. The system can be quickly deployed using the provided `setup.sh` script:

```bash
# Clone the repository
git clone https://github.com/username/ai-cybersecurity-homelab.git
cd ai-cybersecurity-homelab

# Run the setup script with root privileges
sudo ./setup.sh
```

The setup script will:
1. Configure the necessary virtual networks
2. Deploy the required virtual machines
3. Install and configure all security tools
4. Set up the AI integration components
5. Configure the automation workflows
6. Generate comprehensive documentation

## 📜 Usage

The homelab can be controlled through the central management script:

```bash
# Check the status of all services
./homelab.py status

# Start specific services
./homelab.py start [service|all]

# Run a security scan
./homelab.py scan --target [target_name]

# Run AI analysis
./homelab.py ai [blue|red] --input [input_file] --output [output_file]

# Generate documentation
./homelab.py docs

# Push changes to GitLab
./homelab.py push

# Run a demonstration scenario
./homelab.py demo [web-attack|incident-response]
```

## 🧭 Demonstration Scenarios

The homelab includes pre-configured demonstration scenarios:

1. **Web Application Attack**: Demonstrates reconnaissance, vulnerability scanning, and exploitation of a web application with AI analysis
2. **Incident Response**: Simulates an attack, detects it with Wazuh, analyzes it with AI, and demonstrates response procedures

## 📜 Documentation

The complete documentation is accessible via the attack machine at `~/homelab/documentation` and includes:

- Architecture diagrams
- Network configuration details
- VM specifications
- Tool configurations
- AI integration details
- Security practices
- Demo walkthroughs

## 🏫 Learning Resources

This homelab is designed for learning and experimentation. Each component includes detailed explanations and resources for further learning:

- Security tool documentation
- AI integration guides
- Attack and defense methodologies
- Automation best practices

## 📈 Portfolio Value

This project demonstrates several valuable skills:

1. **System Architecture Design**: Complex virtualized environment with proper segmentation
2. **Security Tool Integration**: Integration of diverse security tools into a cohesive system
3. **AI Implementation**: Practical application of AI for cybersecurity tasks
4. **Automation**: Security process automation using modern orchestration tools
5. **Documentation**: Comprehensive technical documentation

## 🪪 License

This project is released under the MIT License. See the LICENSE file for details.

## ⭐ Acknowledgments

This project utilizes numerous open-source tools and resources from the cybersecurity community. Specific acknowledgments are included in the documentation for each component.


[Cilium](https://cilium.io/)

