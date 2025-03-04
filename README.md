# 🏠 Homelab
![Project Status](https://img.shields.io/badge/status-in%20development-orange)  

Overview will go here...

<https://hoytsybersecurity.com>

More details here.

## Introduction

This repo contains all of the configuration and documentation of my homelab.

The purpose of my homelab is to learn and to...

## Cluster Provisioning & Architecture

I use [Talos Linux](https://www.talos.dev/) to set up my machines. I prefer Talos because it is lightweight and minimal, and provides production grade security right out of the box. After running plain Talos for over a year, I switched to using [Sidero Omni](https://www.siderolabs.com/platform/saas-for-kubernetes/) to manage my Talos clusters. Omni allows me to freely add nodes and destroy them, scaling my clusters as desired.

I am currently testing out a new architecture of single-node clusters where the workloads are scheduled on the control plane. A wise man taught me the phrase "no in-place upgrades", and I desire to move in that direction. Instead of one big cluster, I'm now running several. Omni makes this extremely easy.

<table>
    <tr>
        <th>Number</th>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
    <td>1</td>
    <td>Jotunheim</td>
        <td>Contains all end-user applications. Stateless, fully provisioned from code. Can be torn down and spun up within minutes on different hardware.</td>
    </tr>
    <tr>
        <td>2</td>
    <td>Data</td>
        <td>Contains all my databases & state. Multi-node. Can be fully restored from Blob storage.</td>
    </tr>
    <tr>
        <td>3</td>
    <td>Moria</td>
        <td>Private cluster provisioned from private repository.</td>
    </tr>
</table>

## :computer: Hardware

### Nodes

I use a combination of mini pc's, and a Zima Blade single board server for my nodes. The mini PC's are great because they are small yet powerful.

Beelink Mini PC | 32GB DDR4 RAM | 1TB SSD

Beelink Mini PC | 32GB DDR4 RAM | 1TB SSD

Zimablade X86 Single Board Server | 16GB DDR4 RAM | 1TB SSD

### Workstation

Razer Blade 15 | 32GB DDR4 RAM | 1TB SSD

## :rocket: Installed Apps & Tools

### Apps

End User Applications
<table>
    <tr>
        <th>Logo</th>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/commafeed.svg"></td>
        <td><a href="https://www.commafeed.com/#/welcome">Commafeed</a></td>
        <td>Bloat free RSS feed reader</td>
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
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/wallabag-light.svg"></td>
        <td><a href="https://wallabag.org/">Wallabag</a></td>
        <td>Save articles & posts from the web for storage & reading later</td>
    </tr>
</table>

### Infrastructure

Everything needed to run my cluster & deploy my applications
<table>
    <tr>
        <th>Logo</th>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/svg/cert-manager.svg"></td>
        <td><a href="https://cert-manager.io/">Cert Manager</a></td>
        <td>X.509 certificate management for Kubernetes.</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/cilium.svg"></td>
        <td><a href="https://cilium.io/">Cilium</a></td>
        <td>My CNI of choice, used on all clusters. eBPF-based Networking, Observability, Security</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/cloudflare-zero-trust.png"></td>
        <td><a href="https://developers.cloudflare.com/cloudflare-one/">Cloudflare Zero Trust</a></td>
        <td>Used for private tunnels to expose public services (without requiring a public IP).</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/postgresql.svg"></td>
        <td><a href="https://cloudnative-pg.io/">CloudNativePG</a></td>
        <td>Database operator for running PostgreSQL clusters</td>
    </tr>
    <tr>
        <td><img width="32" src="https://www.svgrepo.com/download/530451/dns.svg"></td>
        <td><a href="https://github.com/kubernetes-sigs/external-dns">External DNS</a></td>
        <td>Synchronizes exposed Kubernetes Services and Ingresses with DNS providers.</td>
    </tr>
    <tr>
        <td><img width="32" src="https://www.svgrepo.com/download/477066/lock.svg"></td>
        <td><a href="https://external-secrets.io/latest/">External Secrets Operator</a></td>
        <td>Used to sync my secrets from Azure Key Vaults to my cluster</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/flux-cd.svg"></td>
        <td><a href="https://fluxcd.io/">Flux CD</a></td>
        <td>My GitOps solution of choice. Better than Argo.</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/svg/grafana.svg"></td>
        <td><a href="https://grafana.com/">Grafana</a></td>
        <td>The open observability platform.</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/svg/prometheus.svg"></td>
        <td><a href="https://prometheus.io/">Prometheus</a></td>
        <td>An open-source monitoring system with a dimensional data model, flexible query language, efficient time series database and modern alerting approach.</td>
    </tr>
    <tr>
        <td><img width="32" src="https://www.svgrepo.com/download/374041/renovate.svg"></td>
        <td><a href="https://github.com/renovatebot/renovate">Renovate</a></td>
        <td>Automated dependency updates.</td>
    </tr>
    <tr>
        <td><img width="32" src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/synology.svg"></td>
        <td><a href="https://github.com/SynologyOpenSource/synology-csi">Synology CSI Driver</a></td>
        <td>Used to provision Persistent Volumes directly on my Synology</td>
    </tr>
</table>

## Networking

I use a Unifi Express Router, configured with 7 different VLANs which are all locked down by strict traffic rules.

I use [Cilium](https://cilium.io/) as my CNI. I use LoadBalancer IPAM to assign IP addresses to my LoadBalancer services and use Cilium as an ingress controller. This way, I don't need to install and maintain a seperate ingress controller like Traefik, which I used in the past.

### Storage

I use a Synology DS224+ as a NAS. I use the Synology CSI driver to provision Persistent Volumes from my clusters directly on the NAS. I also have an NFS share for data that needs to be shared between clusters.

## Secret Management

Azure Key Vaults are used to store my secrets. I sync them to my cluster using the External Secrets Operator.
