<!-- SEO Meta: A curated directory of Next-Generation Firewalls (NGFW), Open-Source Firewall Platforms, Intrusion Detection/Prevention Systems (IDS/IPS), and Zero Trust Network Security Architectures. -->
<!-- Keywords: firewall, next-generation firewall, ngfw, network security, opnsense, pfsense, openwrt, cilium, suricata, zeek, crowdsec, snort3, fortigate, palo alto networks, zero trust -->

# Awesome-Firewall-Network-Security

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#how-to-contribute)
[![GitHub Stars](https://img.shields.io/github/stars/ishandutta2007/Awesome-Firewall-Network-Security?style=flat-square&color=yellow)](https://github.com/ishandutta2007/Awesome-Firewall-Network-Security/stargazers)
[![Last Updated](https://img.shields.io/badge/Last%20Updated-October%202026-blue)](https://github.com/ishandutta2007/Awesome-Firewall-Network-Security)

> A curated collection of leading Enterprise Next-Generation Firewalls (NGFW), commercial security appliances, and high-performance open-source network defense projects—covering stateful packet inspection, eBPF micro-segmentation, intrusion prevention (IDS/IPS), and Zero Trust perimeter engineering.

---

## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [Enterprise SaaS & Hosted NGFW Platforms](#saashosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
  - [Architecture Guide: Building an Open-Source Security Stack](#architecture-guide-building-a-resilient-open-source-security-stack)
- [Key Architectural Comparison & Selection Matrix](#key-architectural-comparison--selection-matrix)
- [Frequently Asked Questions (FAQ)](#frequently-asked-questions-faq)
- [How to Contribute](#how-to-contribute)
- [Disclaimer & License](#disclaimer)

---
## Sector Overview & Market Dynamics

The global enterprise firewall and network security market is valued at approximately **$30.8 Billion in 2025** and projected to reach **$34.4 Billion by 2026** (with the dedicated Next-Generation Firewall / NGFW segment accounting for ~$7.1B+), maintaining a robust compound annual growth rate (CAGR) of ~11–13%.

Structurally, the sector exhibits a **concentrated oligopoly at the enterprise tier**—where dominant vendors (Palo Alto Networks, Fortinet, Cisco, and Check Point) command well over 50% of worldwide revenue—balanced by a **moderately fragmented long tail** of specialized UTM hardware providers, cloud-native micro-segmentation platforms, and open-source ecosystems.

## SaaS/Hosted Platforms

| Platform | Company Scale (Revenue / Valuation) | Core Capabilities | Starting Pricing | Free Tier Limits / Evaluation Period |
| :--- | :--- | :--- | :--- | :--- |
| **[Cisco Secure Firewall](https://www.cisco.com/c/en/us/products/security/firewalls/index.html)** | $53.80B Revenue / ~$235B Market Cap (Enterprise Giant) | Enterprise firewall portfolio (formerly Firepower) with deep integration into Cisco network switches, routers, and Talos threat intelligence. | $1.20/hr PAYG (Cloud FTDv) or $450 one-time hardware (Firepower 1010) + $395/yr base threat subscription | **30-day free trial** on AWS/Azure Marketplace (Software fees waived for 30 days for 1 virtual firewall instance; cloud compute infrastructure charges apply) |
| **[Palo Alto Networks](https://www.paloaltonetworks.com/network-security/next-generation-firewall)** | $8.03B Revenue / ~$119B Market Cap (Industry Leader) | Enterprise NGFW platform with deep content inspection, App-ID, WildFire ML threat intelligence, and Prisma Access cloud edge security. | $1.35/hr PAYG (VM-Series software) or $1,800 entry hardware (PA-410) + $650/yr threat prevention subscription | **30-day free trial** for Cloud NGFW (limited to 2 firewalls securing up to 100 GB of traffic) and 30-day VM-Series evaluation license on VMware/Azure/GCP |
| **[Fortinet FortiGate](https://www.fortinet.com/products/next-generation-firewall)** | $5.96B Revenue / ~$72B Market Cap (Global Leader) | Enterprise NGFW powered by custom SPUs/NPUs for ASIC acceleration, native SD-WAN, and centralized FortiManager orchestration. | $480 one-time hardware (FortiGate 40F) + $210/yr FortiCare UTP bundle, or $0.65/hr (FortiGate-VM) | **30-day free trial** for FortiGate-VM on AWS, Azure, and GCP (restricted to 1 vCPU and baseline evaluation license, full UTM inspection features unlocked) |
| **[Untangle NG Firewall (Arista)](https://www.untangle.com/)** | $5.86B Revenue / ~$110B Market Cap (Arista Networks) | NGFW platform for SMB with modular apps for web filtering, IPS, WireGuard VPN, and policy management in Arista Edge Threat Management. | $25.00/month (Complete software package) or $299 one-time hardware (Z4 series appliance) | **Free Forever** basic tier (unlimited duration with baseline routing, NAT, and firewall rules; excludes Web Filter and IPS) + **30-day full-featured trial** |
| **[Juniper SRX](https://www.juniper.net/us/en/products/security/srx-series.html)** | $5.60B Revenue / $14.0B Acquisition (HPE parent ~$29B Rev) | Enterprise security gateway combining high-performance routing, switching, and Junos OS security services with cSRX container support. | $0.55/hr PAYG (vSRX virtual firewall) or $450 one-time hardware (SRX300) + annual security bundle | **60-day free trial** for vSRX directly from Juniper (core firewall enabled for 60 days, advanced IPS & AppSecure active for first 30 days); 30 days via cloud marketplaces |
| **[Check Point Quantum](https://www.checkpoint.com/quantum/)** | $2.40B Revenue / ~$20.6B Market Cap (Perimeter Pioneer) | Enterprise security gateway with unified threat management, SandBlast zero-day threat extraction, and centralized management console. | $1,050 one-time hardware (Quantum Spark 1530 SMB appliance) + $350/yr Threat Prevention suite, or $0.85/hr (CloudGuard) | **30-day free trial** (Quantum Virtual/CloudGuard evaluation license providing complete Next-Gen Threat Prevention and sandboxing blades) |
| **[Sophos Firewall](https://www.sophos.com/en-us/products/firewall)** | $1.20B Revenue / $3.9B PE Valuation (Thoma Bravo) | Commercial NGFW with synchronized endpoint protection, cloud sandbox, and Sophos Central for multi-site orchestration. | $580 one-time hardware (XGS 87 desktop) + $260/yr Standard Protection subscription | **Free Forever** for home non-commercial use (Home Edition limited to 4 CPU cores, 6 GB RAM, full feature set on dedicated PC); **30-day free trial** for enterprise virtual appliance |
| **[Barracuda CloudGen Firewall](https://www.barracuda.com/products/cloudgen-firewall)** | ~$600M ARR / $4.0B PE Valuation (KKR) | Enterprise firewall engineered for distributed multi-site networks with SD-WAN optimization and CloudGen Control Center. | $750 one-time hardware (CloudGen F18) or $0.70/hr PAYG on AWS/Azure | **14-day free trial** directly through Barracuda platform (full-featured CloudGen evaluation) or **30-day trial** via AWS Marketplace (software costs waived) |
| **[SonicWall](https://www.sonicwall.com/products/firewalls/)** | ~$400M ARR / $1.5B PE Valuation (Francisco Partners) | NGFW and UTM appliances for SMB and distributed mid-market with Capture ATP multi-engine sandboxing and Capture Security Center. | $495 one-time hardware (SonicWall TZ270) + $195/yr Essential Protection Service Suite (EPSS) | **30-day free trial** (MySonicWall virtual NSv trial with full Capture ATP cloud sandbox enabled; promotional trials up to 90 days) |
| **[WatchGuard Firebox](https://www.watchguard.com/wgrd-products/network-security/firebox)** | ~$250M ARR / $1.0B PE Valuation (Vector Capital) | Mid-market NGFW with integrated Wi-Fi, VPN, and threat detection, managed via WatchGuard Cloud or on-premises Dimension. | $390 one-time hardware (Firebox T25) + $150/yr Standard Support, or $0.45/hr (Firebox Cloud PAYG) | **30-day free trial** (Total Security Suite evaluation key providing complete Gateway AV, Intrusion Prevention, and WebBlocker on physical or virtual instances) |

## Open-Source GitHub Projects

Curated open-source firewall platforms, intrusion prevention systems, and network security tooling—sorted strictly descending by GitHub stars. Each repository badge links directly to its stargazers page.

- **[OpenWrt](https://github.com/openwrt/openwrt)** [![GitHub stars](https://img.shields.io/github/stars/openwrt/openwrt?style=social&color=white)](https://github.com/openwrt/openwrt/stargazers)  
  Linux-based embedded operating system and router firmware equipped with `nftables`/`iptables` stateful packet filtering, SQM QoS bufferbloat management, and multi-WAN load balancing. Extensively extensible via thousands of opkg packages (including Suricata, AdGuard Home, and WireGuard) across x86 hardware and commercial routers.

- **[Cilium](https://github.com/cilium/cilium)** [![GitHub stars](https://img.shields.io/github/stars/cilium/cilium?style=social&color=white)](https://github.com/cilium/cilium/stargazers)  
  Cloud-native networking, observability, and network security firewall powered by eBPF. Enforces Layer 3 through Layer 7 identity-aware security policies, transparent network encryption (WireGuard / IPsec), and API-level authorization (HTTP/gRPC/Kafka) without iptables overhead.

- **[CrowdSec](https://github.com/crowdsecurity/crowdsec)** [![GitHub stars](https://img.shields.io/github/stars/crowdsecurity/crowdsec?style=social&color=white)](https://github.com/crowdsecurity/crowdsec/stargazers)  
  Collaborative, crowd-sourced cyber defense engine that parses system and network logs to detect aggressive behaviors, blocking malicious IPs across the collective network. Integrates as an automated remediation bouncer with OPNsense, pfSense, Linux nftables, and cloud firewalls.

- **[OpenSnitch](https://github.com/evilsocket/opensnitch)** [![GitHub stars](https://img.shields.io/github/stars/evilsocket/opensnitch?style=social&color=white)](https://github.com/evilsocket/opensnitch/stargazers)  
  Interactive GNU/Linux application firewall inspired by Little Snitch. Intercepts outgoing connection requests in real-time, displays interactive alert prompts, and allows or blocks connections based on process binary, user ID, destination IP, and domain patterns.

- **[ntopng](https://github.com/ntop/ntopng)** [![GitHub stars](https://img.shields.io/github/stars/ntop/ntopng?style=social&color=white)](https://github.com/ntop/ntopng/stargazers)  
  High-speed web-based traffic analysis, flow monitoring, and network security inspection software. Leverages nDPI (deep packet inspection) to categorize application layer traffic, identify malicious behavior, surface security vulnerabilities, and enforce host-level policy actions.

- **[Zeek](https://github.com/zeek/zeek)** [![GitHub stars](https://img.shields.io/github/stars/zeek/zeek?style=social&color=white)](https://github.com/zeek/zeek/stargazers)  
  Enterprise-scale network security monitoring (NSM) framework that translates raw network traffic into structured, transaction-level event streams. Enables in-depth threat hunting, forensic analysis, protocol validation, and automated network anomaly alerting.

- **[ClamAV](https://github.com/Cisco-Talos/clamav)** [![GitHub stars](https://img.shields.io/github/stars/Cisco-Talos/clamav?style=social&color=white)](https://github.com/Cisco-Talos/clamav/stargazers)  
  Open-source multi-threaded antivirus engine designed for scanning email gateways, network proxies, and file endpoints against trojans, viruses, and malware. Regularly deployed as an inline content scanning module within open-source perimeter firewalls.

- **[Suricata](https://github.com/OISF/suricata)** [![GitHub stars](https://img.shields.io/github/stars/OISF/suricata?style=social&color=white)](https://github.com/OISF/suricata/stargazers)  
  High-performance, multi-threaded Network Threat Detection, IDS, IPS, and Network Security Monitoring engine. Uses standard rule formats (ETOpen/ETPro) and hyperscan acceleration; serves as the foundational intrusion prevention engine in OPNsense, pfSense, and numerous enterprise firewalls.

- **[pfSense](https://github.com/pfsense/pfsense)** [![GitHub stars](https://img.shields.io/github/stars/pfsense/pfsense?style=social&color=white)](https://github.com/pfsense/pfsense/stargazers)  
  Established FreeBSD-based open-source firewall distribution providing stateful packet filtering via `pf`, multi-WAN failover, OpenVPN/IPsec endpoints, and extensive package support. Backed by Netgate, offering pfSense Community Edition (CE) and commercial pfSense Plus.

- **[OPNsense](https://github.com/opnsense/core)** [![GitHub stars](https://img.shields.io/github/stars/opnsense/core?style=social&color=white)](https://github.com/opnsense/core/stargazers)  
  Leading open-source FreeBSD-based firewall and routing platform. Features a modern MVC web interface, native WireGuard VPN, integrated Suricata IDS/IPS, weekly security patches, and human-readable XML configuration for Git version control and auditable infrastructure.

- **[Snort 3](https://github.com/snort3/snort3)** [![GitHub stars](https://img.shields.io/github/stars/snort3/snort3?style=social&color=white)](https://github.com/snort3/snort3/stargazers)  
  Completely modernized multi-threaded network intrusion detection and prevention system (IDS/IPS). Features Lua scripting configuration, Hyperscan pattern matching, shared connection state tables, and real-time packet inspection backed by Cisco Talos intelligence.

- **[Firewalld](https://github.com/firewalld/firewalld)** [![GitHub stars](https://img.shields.io/github/stars/firewalld/firewalld?style=social&color=white)](https://github.com/firewalld/firewalld/stargazers)  
  Dynamically managed Linux firewall daemon supporting network/firewall zones, runtime rule reconfiguration via D-Bus without breaking existing connections, and native backend support for both `nftables` and `iptables`.

- **[VyOS](https://github.com/vyos/vyos-1x)** [![GitHub stars](https://img.shields.io/github/stars/vyos/vyos-1x?style=social&color=white)](https://github.com/vyos/vyos-1x/stargazers)  
  Debian-based open-source network operating system delivering enterprise routing (BGP, OSPF), zone-based stateful firewalling, source/destination NAT, and multi-tunnel VPN termination managed through a unified declarative CLI and HTTP API.

- **[Aegis](https://github.com/pushkar-gr/Aegis)** [![GitHub stars](https://img.shields.io/github/stars/pushkar-gr/Aegis?style=social&color=white)](https://github.com/pushkar-gr/Aegis/stargazers)  
  High-performance distributed Zero Trust firewall leveraging eBPF/XDP. Enforces identity-based micro-segmentation directly inside the Linux kernel, opening network pathways strictly upon authenticated user verification.

- **[Open-NGFW](https://github.com/hungtrungthinh/Open-NGFW)** [![GitHub stars](https://img.shields.io/github/stars/hungtrungthinh/Open-NGFW?style=social&color=white)](https://github.com/hungtrungthinh/Open-NGFW/stargazers)  
  Modern Next-Generation Firewall engine developed in Rust featuring a clean web UI dashboard, real-time traffic monitoring, RESTful API management, and containerized Docker deployment across x86_64 and ARM platforms.

### Architecture Guide: Building a Resilient Open-Source Security Stack

- **Perimeter Edge Defense**: Deploy **OPNsense** or **OpenWrt** on dedicated hardware appliances (e.g., Protectli, Lanner) for gateway firewalling and NAT.
- **Deep Packet Inspection & IPS**: Embed **Suricata** or **Snort 3** with community rule feeds (Emerging Threats ETOpen) to detect exploit attempts and command-and-control traffic.
- **Collaborative IP Bouncing**: Pair **CrowdSec** bouncers with your edge firewalls to block active threat campaigns identified across the global threat network.
- **Cloud-Native & Container Firewalls**: Leverage **Cilium** for eBPF-driven L3-L7 micro-segmentation in Kubernetes environments.
- **Configuration-as-Code**: Store your firewall XML configurations (OPNsense) or declarative scripts (VyOS) in a version-controlled Git repository to ensure automated auditing and zero-downtime recovery.



## Key Architectural Comparison & Selection Matrix

When selecting between commercial enterprise platforms and open-source firewall distributions, evaluate the following operational tradeoffs:

| Feature Dimension | Commercial SaaS / Enterprise NGFW | Open-Source Firewall Distributions |
| :--- | :--- | :--- |
| **Primary Deployment** | Proprietary turnkey hardware or hypervisor/cloud virtual appliances | Commodity x86 hardware (Protectli, Lanner), VMs, or container/eBPF runtimes |
| **Throughput Acceleration** | Proprietary ASICs (e.g., Fortinet SPU/NPU) or custom offload cards | Modern CPU instruction sets (DPDK, AES-NI, eBPF/XDP kernel bypass) |
| **Threat Intelligence** | Cloud threat intelligence feeds (Talos, WildFire, FortiGuard) | Community intelligence feeds (ETOpen, CrowdSec CTI, URLhaus) with optional paid feeds |
| **Multi-Site Orchestration**| Centralized vendor cloud console (Sophos Central, FortiManager) | Declarative configuration-as-code (GitOps, Ansible, XML syncing, Terraform) |
| **Licensing Cost** | Annual recurring subscription per appliance or metered hourly | 100% free perpetual software license; hardware CapEx and in-house maintenance only |
| **Auditability & Privacy** | Proprietary closed-source firmware | 100% auditable source code with zero telemetry leakage and full data sovereignty |


## Frequently Asked Questions (FAQ)

### What is the primary difference between a traditional firewall and a Next-Generation Firewall (NGFW)?
Traditional firewalls operate primarily at Layers 3 and 4, inspecting source and destination IP addresses, ports, and protocols (stateful packet filtering). Next-Generation Firewalls (NGFW) perform Layer 7 deep packet inspection (DPI), detecting application-layer signatures regardless of port, enforcing TLS/SSL inspection, blocking zero-day threats through sandboxing, and providing integrated intrusion prevention (IPS).

### Which open-source firewall is best: OPNsense, pfSense, or OpenWrt?
- **OPNsense**: Best for modern enterprise and homelab deployments needing active weekly patching, intuitive modern UI, native WireGuard support, and plaintext XML Git versioning.
- **pfSense (CE)**: Best for users looking for extensive historical documentation and battle-tested FreeBSD stability, though the community version receives fewer updates than pfSense Plus.
- **OpenWrt**: Best for resource-constrained embedded routers, IoT gateways, and lightweight edge environments requiring minimal CPU and memory footprints.

### How does eBPF change network firewall architectures?
Frameworks like **Cilium** and **Aegis** leverage eBPF (Extended Berkeley Packet Filter) to attach security filtering programs directly to Linux kernel hooks and the network driver (XDP). This bypasses the traditional `iptables` connection tracking bottleneck, enabling millions of packet evaluations per second with identity-based micro-segmentation for Kubernetes and cloud-native containers.

## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Commercial firewalls require subscription renewals for threat intelligence and support; open-source solutions shift costs to hardware, maintenance, and staff expertise .

- Open-source firewalls have no vendor RMA—organizations must maintain spare hardware and configuration backups independently.

- OPNsense and pfSense share a common ancestry but have diverged significantly; evaluate update cadence, WireGuard support, and philosophical alignment before choosing .



---



**Made for network administrators, security engineers, homelab enthusiasts, and organizations building transparent, auditable perimeter defense.**  

Let's make network security more open, controllable, and accessible.
