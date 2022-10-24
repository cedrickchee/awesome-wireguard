# Awesome WireGuard [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

<br />
<div align="center">
  <img width="581" src="https://raw.githubusercontent.com/cedrickchee/awesome-wireguard/master/assets/banner.png">
</div>
<br />

> A curated list of WireGuard tools, projects, and resources.

WireGuard® - fast, modern, secure VPN tunnel.

_You can see the updates on [Twitter](https://twitter.com/awesome-wireguard) (coming soon)_

> Please, help organize these resources so that they are easy to find and understand for newcomers. See how to [Contribute][contributing] for tips!

_If you see a link here that is not (any longer) a good fit, you can fix it by submitting a [pull request][editreadme] to improve this file. Thank you!_

## Contents

<details>

<summary><b>Expand Table of Contents</b></summary>

- [What is WireGuard](#what-is-wireguard)
- [Official Resources](#official-resources)
- [Where to Start](#where-to-start)
- [Projects](#projects)
  - [Tools](#tools)
  - [Mesh Network](#mesh-network)
  - [Deployment](#deployment)
    - [Container](#container)
  - Monitoring
  - Security
    - Protocol
    - Encryption
  - Runtime
  - [User Interface](#user-interface)
    - [Terminal / CLI](terminal--cli)
    - [Web](#web)
    - [Desktop](#desktop)
    - [Dashboards](#dashboards)
  - Development
    - Development Environment
    - Testing
    - Boilerplate
  - Homeserver
  - [Services based on WireGuard](#services-based-on-wireguard)
    - [Cloud Service](#cloud-service)
    - [VPN](#vpn)
  - [Extensions / Plugins](#extensions--plugins)
  - Optimization
  - Language Bindings
  - [Alternative Implementations](#alternative-implementations)
- [Useful Resources](#useful-resources)
  - [Blog Posts](#blog-posts)
  - [Articles](#articles)
  - [Demos and Examples](#demos-and-examples)
  - [Good Tips](#good-tips)
  - [Tutorials](#tutorials)
  - [Videos](#videos)
  - [Books](#books)
  - [Podcasts and Interviews](#podcasts-and-interviews)
  - [Presentations](#presentations)
  - [Newsletters](#newsletters)
- Uncategorized
- [Communities and Meetups](#communities-and-meetups)
  - [English](#english)
  - Chinese

</details>

---

## What is WireGuard

> WireGuard® is an extremely simple yet fast and modern VPN that utilizes 
> state-of-the-art cryptography. It aims to be faster, simpler, leaner, and more 
> useful than IPsec, while avoiding the massive headache. It intends to be 
> considerably more performant than OpenVPN. WireGuard is designed as a general 
> purpose VPN for running on embedded interfaces and super computers alike, 
> fit for many different circumstances. Initially released for the Linux kernel, 
> it is now cross-platform (Windows, macOS, BSD, iOS, Android) and widely 
> deployable. It is currently under heavy development, but already it might 
> be regarded as the most secure, easiest to use, and simplest VPN solution 
> in the industry.

_Source: [Official WireGuard project website](https://www.wireguard.com/)_

## Official Resources
  
- [Next Generation Kernel Network Tunnel](https://www.wireguard.com/papers/wireguard.pdf) [PDF] - Whitepaper.
- [WireGuard Docs](https://github.com/pirate/wireguard-docs) - Unofficial WireGuard documentation.

## Where to Start

- [Quick Start](https://www.wireguard.com/quickstart/) - Official quick start.

---

## Projects

### Tools

- [wg-quick](https://git.zx2c4.com/wireguard-tools/about/src/man/wg-quick.8) - Official cross-platform tool to set up a WireGuard interface simply.
- [easy-wg-quick](https://github.com/burghardt/easy-wg-quick) - Creates Wireguard configuration for hub and peers with ease.
- [dsnet](https://github.com/naggie/dsnet/) - Simple command to manage a centralised wireguard VPN. Think wg-quick but quicker: key generation + address allocation.
- [wgctrl](https://github.com/WireGuard/wgctrl-go) - Package wgctrl enables control of WireGuard interfaces on multiple platforms.
- [wgzero](https://github.com/finzzz/wgzero) - Zero overhead wireguard setup.
- [wg-make](https://github.com/tevino/wg-make) - A tool to help set up WireGuard based networks. Currently, it generates configurations for peers according to a single configuration file.
- [onetun](https://github.com/aramperes/onetun) - A user-space WireGuard port-forwarder -- access ports running on peers in your WireGuard network from any device; without having to install WireGuard locally or without root access (no iptables configs).
- [wireproxy](https://github.com/octeep/wireproxy) - A userspace WireGuard client that connects to a WireGuard peer, and exposes a SOCKS5 proxy. (Use cases: Setting up WG as a VPN requires special privilege. It tells the kernel to create a special network interface to handle WG connection. This can get messy if you do not have any special permission (i.e., root), if you do not have proper firewall configuration, or if you want to connect to multiple WG peers at once. wireproxy static tunneling is basically openssh `-D`, which supports SOCKS5 protocols.)
- [wireguard-manager-and-api](https://github.com/Mawthuq-Software/wireguard-manager-and-api) - A tool for rotating the keys on peers to increase their privacy by removing their IP address from memory.

### Mesh Network

- [Tailscale](https://tailscale.com/) - Tailscale is a WireGuard-based app that makes secure, private networks easy for teams of any scale.
- [Headscale](https://github.com/juanfont/headscale) - An open source implementation of the Tailscale control server.
- [innernet](https://github.com/tonarino/innernet) - A private network system that uses WireGuard under the hood. It is similar in its goals to Slack's nebula or Tailscale.
- [Kilo](https://github.com/squat/kilo) - Kilo is a multi-cloud network overlay built on WireGuard and designed for Kubernetes (k8s + wg = kg).
- [NetBird](https://github.com/netbirdio/netbird) - (Previously Wiretrustee) NetBird is an open-source VPN management platform built on top of WireGuard® making it easy to create secure private networks for your organization or home. Technically, it creates an overlay network using ICE protocol (WebRTC) to negotiate P2P connections and WG (kernel module, when possible) to create a fast and encrypted tunnel between machines, falling back to relay (TURN) in case a P2P connection isn't possible. Pretty much just a client app is needed, the rest is done by the software. Their vision is to go beyond traditional VPN by bringing advanced NetSec (Zero Trust security model) like OpenZiti.
- [wesher](https://github.com/costela/wesher) - wesher creates and manages an encrypted mesh overlay network across a group of nodes.
- [gravitl/netmaker](https://github.com/gravitl/netmaker) - Netmaker is a VPN platform that automates WireGuard from homelab to enterprise. The key distinctions in their solutions are: fast because it can use kernel WireGuard (instead of userspace WireGuard, which is slower), tailored towards the Cloud and Kubernetes, and fully self-hostable.
- [HarvsG/WireGuardMeshes](https://github.com/HarvsG/WireGuardMeshes) - Compare WireGuard mesh tools.
- Not Wireguard-based
  - [Tinc](https://www.tinc-vpn.org/) - tinc is a VPN daemon that uses tunnelling and encryption to create a secure private network between hosts on the Internet.
  - [Nebula](https://github.com/slackhq/nebula) - Slack's Nebula is a scalable overlay networking tool.
  - [Zerotier](https://zerotier.com) - Directly Connecting the World's Devices with Universal Software Defined Networking.

### Deployment

- [WireHole](https://github.com/IAmStoxe/wirehole) - A combination of WireGuard, Pi-hole, and Unbound in a docker-compose project with the intent of enabling users to quickly and easily create a personally managed full or split-tunnel WireGuard VPN with ad blocking capabilities thanks to Pi-hole, and DNS caching, additional privacy options, and upstream providers via Unbound.
- [Autowire](https://github.com/elghazal-a/autowire) - Automatically configure Wireguard interfaces in distributed system. It supports Consul as backend.
- [Cloudblock](https://github.com/chadgeary/cloudblock) - Deploys WireGuard VPN, Pi-Hole DNS Ad-blocking, and DNS over HTTPS in a cloud provider - or locally - using Terraform and Ansible.
- [ansible-role-wireguard](https://github.com/githubixx/ansible-role-wireguard) - Ansible role for installing WireGuard VPN. Supports Ubuntu, Debian, Archlinx, Fedora and CentOS.
- [terraform-aws-wireguard](https://github.com/jmhale/terraform-aws-wireguard) - Terraform module to deploy WireGuard on AWS.
- [Firezone](https://github.com/firezone/firezone) - An open-source WireGuard-based VPN server alternative to OpenVPN Access Server. You can self-host this.
- [Algo VPN](https://github.com/trailofbits/algo) - Set up a DIY/personal VPN in the cloud. It is a set of Ansible scripts that simplify the setup of a personal WireGuard and IPsec VPN, open-sourced by Trail of Bits.
- [Place1/wg-access-server](https://github.com/Place1/wg-access-server) - An all-in-one WireGuard VPN solution with a Web UI for connecting devices. This project aims to deliver a simple VPN solution for developers, homelab enthusiasts and anyone else feeling adventurous.
- [WirtBot](https://github.com/b-m-f/WirtBot) - Think of it as a component that will allow you to extend your LAN over the Internet. WirtBot simplifies the process of creating your own private network into 3 steps. No registration, no accounts - Just a network that belongs to you. And it will always be completely free (except for the server/VPS you run it on).
- [seashell/drago](https://github.com/seashell/drago) - A self-hosted and flexible configuration manager designed to make it simple to configure secure network overlays spanning heterogeneous nodes via a Web UI.

#### Container

- [linuxserver/docker-wireguard](https://github.com/linuxserver/docker-wireguard) - A WireGuard container image brought to you by LinuxServer.io. Not all image authors are as great as LinuxServer.io team.
- [cmulk/wireguard-docker](https://github.com/cmulk/wireguard-docker) - A Docker image and configuration for a simple personal VPN, used for the goal of security over insecure (public) networks, not necessarily for Internet anonymity. There are currently 3 flavors.
- [masipcat/wireguard-go-docker](https://github.com/masipcat/wireguard-go-docker) - WireGuard docker image.

### Monitoring

- [MindFlavor/prometheus_wireguard_exporter](https://github.com/MindFlavor/prometheus_wireguard_exporter) - A Prometheus exporter for WireGuard, very light on your server resources.

### Security

####  Protocol

#### Encryption

### Runtime

### User Interface

#### Terminal / CLI

- [WireGuard in NetworkManager](https://blogs.gnome.org/thaller/2019/03/15/wireguard-in-networkmanager/) - Linux NetworkManager has WireGuard support.
- [WireGuard installer](https://github.com/angristan/wireguard-install) - WireGuard VPN installer for Linux servers.
- [PiVPN](https://github.com/pivpn/pivpn) - The Simplest VPN installer (scripts), designed for Raspberry Pi.
- [wireguard-install](https://github.com/Nyr/wireguard-install) - WireGuard road warrior installer for Ubuntu, Debian, CentOS and Fedora.
- [WireGuard-Manager](https://github.com/complexorganizations/wireguard-manager) - enables you to build your own vpn under a minute.
- [wg-meshconf](https://github.com/k4yt3x/wg-meshconf) - WireGuard full mesh configuration generator.
- [tun2socks](https://github.com/xjasonlyu/tun2socks) - Powered by gVisor TCP/IP stack.
- [guard](https://github.com/stellarproject/guard) - A gRPC server for managing wireguard tunnels.
- [docker-wireguard-socks-proxy](https://github.com/kizzx2/docker-wireguard-socks-proxy) - Expose a WireGuard tunnel as a SOCKS5 proxy.
- [wgctl](https://github.com/apognu/wgctl) - Utility to configure and manage your WireGuard tunnels.
- [Wiresteward](https://github.com/utilitywarehouse/wiresteward) - A WireGuard peer manager with OAuth2 authentication.
- [psyhomb/wireguard-tools](https://github.com/psyhomb/wireguard-tools) - WireGuard helper scripts.

#### Web

- [vx3r/wg-gen-web](https://github.com/vx3r/wg-gen-web) - Simple Web based configuration generator for WireGuard.
- [Subspace](https://github.com/subspacecommunity/subspace) - A simple WireGuard VPN server GUI.
- [WireGuard UI](https://github.com/EmbarkStudios/wg-ui) - WireGuard Web UI for self-serve client configurations, with optional auth.
- [WeeJeWel/wg-easy](https://github.com/WeeJeWel/wg-easy/) - The easiest way to run WireGuard VPN + Web-based Admin UI.

#### Desktop

- [network-manager-wireguard](https://github.com/max-moser/network-manager-wireguard) - Network-Manager VPN Plugin for WireGuard.
- [WireGuardStatusbar](https://github.com/aequitas/macos-menubar-wireguard) - macOS menubar icon for WireGuard/wg-quick.

#### Dashboards

- [Wireguard Dashboard](https://github.com/donaldzou/wireguard-dashboard) - A simple and easy to use WireGuard dashboard written in Python and Flask.

### Development

#### Development Environment

#### Testing

#### Boilerplate

### Homeserver

### Services based on WireGuard

#### Cloud Service

- [Warp](https://blog.cloudflare.com/1111-warp-better-vpn/) - A free WireGuard VPN from Cloudflare that's trying to fix mobile Internet performance and security.
- [wgcf](https://github.com/ViRb3/wgcf) - Cross-platform, unofficial CLI for Cloudflare Warp.

#### VPN

- [Mullvad](https://github.com/mullvad/mullvadvpn-app)
- [MozWire](https://github.com/NilsIrl/MozWire) - An unofficial configuration manager giving Linux, macOS users (among others), access to Mozilla VPN.

### Extensions / Plugins

- [wgsd](https://github.com/jwhited/wgsd) - A CoreDNS plugin that serves WireGuard peer information via DNS-SD (RFC6763) semantics. This enables use cases such as mesh networking, NAT-to-NAT connectivity, and dynamic discovery of WireGuard endpoint.

### Optimization

- [nr-wg-mtu-finder](https://github.com/nitred/nr-wg-mtu-finder) - A Python project to help you find the optimal MTU values for WG server and WG peer that maximizes the upload or download speeds between a peer and server.

### Language Bindings

### Alternative Implementations

- [boringtun](https://github.com/cloudflare/boringtun) - Userspace WireGuard implementation in Rust by Cloudflare.

## Useful Resources

### Blog Posts

- [WireGuard: great protocol, but skip the Mac app](https://rachelbythebay.com/w/2020/12/24/wg/)
- [WireGuard on Kubernetes with Adblocking](https://codingcoffee.dev/blog/wireguard_on_kubernetes_with_adblocking/)
- [SSH and User-mode IP WireGuard](https://fly.io/blog/ssh-and-user-mode-ip-wireguard/)
- [Setup and Adblocking VPN Using WireGuard and NextDNS](https://blog.paramdeo.com/2019/07/03/setup-an-adblocking-vpn-using-wireguard-and-nextdns.html)
- [WireGuard Endpoint Discovery and NAT Traversal using DNS-SD](https://www.jordanwhited.com/posts/wireguard-endpoint-discovery-nat-traversal/)
- [Taildrop was kind of easy, actually](https://tailscale.com/blog/2021-06-taildrop-was-easy/) - Taildrop was the main new feature launched in Tailscale v1.8.
- [IPv6 WireGuard Peering at Fly.io](https://fly.io/blog/ipv6-wireguard-peering/)
- [Our User-Mode WireGuard Year](https://fly.io/blog/our-user-mode-wireguard-year/)
- [Tunnel WireGuard via WebSockets](https://kirill888.github.io/notes/wireguard-via-websocket/) - Setting up WireGuard to work in restricted networks that block UDP traffic.
- [Tailscale's human-scale networks are still controlled by Google and Microsoft](https://iliana.fyi/blog/tailscale-auth-and-threat-modeling/)
- [How to access a peer's local network](https://iliasa.eu/wireguard-how-to-access-a-peers-local-network/) - A simple solution. There is no need of any configurations to set split-tunneling. The example shows how Peer B can route to Peer A through a WG server. Peer B can reach a specific network (subnet) behind Peer A.
- [Routing Specific Docker Containers Through WireGuard VPN with systemd-networkd](https://www.eisfunke.com/article/docker-wireguard-systemd.html) - A simple solution for routing specific docker containers through a WireGuard VPN using only two simple systemd-networkd files, no cumbersome `wg` or `ip` calls.

### Articles

- [In-kernel WireGuard is on its way to FreeBSD and the pfSense router](https://arstechnica.com/gadgets/2021/03/in-kernel-wireguard-is-on-its-way-to-freebsd-and-the-pfsense-router/)
- [It's Looking Like Android Could Be Embracing WireGuard - "A Sane VPN"](https://www.phoronix.com/scan.php?page=news_item&px=WireGuard-Android-GKI-Enabled)
- [Tailscale Raises $100 Million Series B to Fix the Internet with its Zero Trust VPN for Modern DevOps Teams](https://www.businesswire.com/news/home/20220504005325/en)
- [Identity management for WireGuard](https://lwn.net/SubscriberLink/910766/7678f8c4ede60928/)

### Demos and Examples

### Good Tips

- [WireGuard Gotchas with Multiple Tunnels](https://casavant.org/2020/10/10/wireguard-fwmark.html) - WG has a bit of a trap/gotcha when running multiple independent tunnels, one of which has a default route associated with it.

### Tutorials

- [How to easily configure WireGuard](https://www.stavros.io/posts/how-to-configure-wireguard/)
- [Getting Started with WireGuard](https://miguelmota.com/blog/getting-started-with-wireguard/)
- [What They Don’t Tell You About Setting Up A WireGuard VPN](https://dev.to/tangramvision/what-they-don-t-tell-you-about-setting-up-a-wireguard-vpn-1h2g)
- [Building a simple VPN with WireGuard with a Raspberry Pi as Server](https://snikt.net/blog/2020/01/29/building-a-simple-vpn-with-wireguard-with-a-raspberry-pi-as-server/)
- [Setting up a home VPN server with Wireguard (macOS)](https://mikkel.hoegh.org/2019/11/01/home-vpn-server-wireguard/)
- [Creating a VPN Gateway with a Unikernel running WireGuard](https://nanovms.com/dev/tutorials/running-nanos-wireguard-vpn-gateway)
- [Directions for setting up a WireGuard bounce server](https://gitlab.com/ncmncm/wireguard-bounce-server)
  > I find plenty of tutorials online for setting up the most basic Wireguard apparatus.
  > Like most peoples', my machines are stuck behind NATs. To connect between NATted hosts, you need control of a host that is not, to keep up on what external addresses the NATs are presenting.
  > The docs for WireGuard mention bounce servers, but say nothing about how to set one up.
- [WireGuard VPN Road Warrior Setup](https://emanuelduss.ch/2018/09/29/wireguard-vpn-road-warrior-setup/) - The important feature of this setup is, split tunnelling.
  > Either all traffic (default route) or only the traffic desired for the internal network can be routed through the VPN (split tunneling). This can be configured on the client.
- [Routing Docker Host And Container Traffic Through WireGuard](https://www.linuxserver.io/blog/routing-docker-host-and-container-traffic-through-wireguard) using [WireGuard Docker image by linuxserver.io](https://github.com/linuxserver/docker-wireguard)

### Videos

- [WireGuard: Next Generation Abuse-Resistant Kernel Network Tunnel](https://www.youtube.com/watch?v=eYztYCbV_8U)- A good talk from the WireGuard developer and security researcher, Jason Donenfeld explaining what WireGuard can do and how it works. The talk examine both the cryptography and kernel implementation particulars of WireGuard and explore an offensive attack perspective on network tunnels.
- [How To Build Your Own Wireguard VPN Server in The Cloud](https://www.youtube.com/watch?v=7yC-gJtl9mQ) - A good tutorial from Lawerence Systems regarding WireGuard.

### Books

### Podcasts and Interviews

### Presentations

- [Presentations by Jason A. Donenfeld](https://www.wireguard.com/presentations/) - A list of all Jason's presentations.

### Newsletters

## Uncategorized

- [WebVM: Linux Virtualization in WebAssembly with Full Networking via Tailscale](https://leaningtech.com/webvm-virtual-machine-with-networking-via-tailscale/) - Run WireGuard and Tailscale in the browser. wireguard-go code compiled to Wasm. WebVM is proprietary WebAssembly-powered x86 virtualization tech. I'm genuinely curious how it compares to v86/Fabrice Bellard's JSLinux (like WebVM but free and opened-source).

## Communities and Meetups

### English

- [/r/WireGuard](https://www.reddit.com/r/WireGuard/) - Official Reddit WireGuard.
- [#wireguard on Libera](https://web.libera.chat/#wireguard) - Official IRC on Libera Chat.

### Chinese

## Contribute

Contributions welcome! If you would like to contribute, please read the [contribution guidelines][contributing] first. It contains a lot of tips and guidelines to help keep things organized.

_Future: Implement GitHub Actions to monitor and verify all the links with a simple [Node.js script](./scripts/pull_request.js)_

## Copyright

"WireGuard" and the "WireGuard" logo are registered trademarks of Jason A. Donenfeld.

## License

<details>

<summary><b>Expand License</b></summary>

This repository contains a variety of content; some developed by Cedric Chee, 
and some from third-parties. The third-party content is distributed under the 
license provided by those parties.

*I am providing code and resources in this repository to you under an open 
source license. Because this is my personal repository, the license you receive 
to my code and resources is from me and not my employer.*

The content developed by Cedric Chee is distributed under the following license:

### Text

The text content is released under the CC-BY-NC-ND license.
Read more at [Creative Commons](https://creativecommons.org/licenses/by-nc-nd/3.0/us/legalcode).

### Code

The code in this repository is released under the [MIT license](LICENSE).
</details>

[editreadme]: https://github.com/cedrickchee/awesome-wireguard/edit/main/README.md
[contributing]: https://github.com/cedrickchee/awesome-wireguard/blob/main/.github/CONTRIBUTING.md
