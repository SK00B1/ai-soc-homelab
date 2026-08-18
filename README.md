ai-soc-homelab

A small SOC-style cybersecurity homelab I'm building using virtual machines.

The goal is to end up with something that actually works end to end. An attacker machine that generates suspicious activity, a monitored machine that produces logs, a SIEM that collects those logs and raises alerts, and a Python + AI layer that helps explain what an alert means and what an analyst should check next.

I'm building this to learn how detection and investigation actually work in practice.

Why I'm building it? 

Reading about SIEMs and log analysis is one thing. Actually setting one up, breaking it, fixing it, and then generating real activity to see whether it gets detected is a different thing. I wanted a lab where I could:

generate controlled suspicious activity and watch it show up in logs
see what an alert actually looks like from a defender's side
practise investigating an alert instead of just reading about the theory
have something concrete I can explain in an interview

Everything here runs on machines I own and control. It's a defensive lab.

Where it's at now: 
Two VMs exist and they can reach each other. No Wazuh yet so no victim machine. 

Done:
-  Both VMs built and booting (Ubuntu Server LTS, ARM64, UTM)
- Tools installed on the attacker
- Networking tested and confirmed between the two

NOT Done :
- Victim VM
- Wazuh install and agents
- Any actual attacks
- Python alert parsing
- AI part

STACK: UTM on Apple Silicon for the VMs, Ubuntu Server 26.04 LTS on both of them, map and tcpdump and nectar on the attacker side, Wazuh for the SIEM once I get there, python 3 for the parsing, git for logging progress. 

KALI: Originally wanted Kali as the attacker machine. I'm on M-series MAC so I got the ARM64 installer and both the graphical and the text installer failed before it got anywhere.
I switched the attacker to Ubuntu and installed the tools I actually needed. Kali is Debian with security tools already on it, and all of those tools are in Ubuntu's repos, so I wasn't really losing anything except the convenience. Writeup is in docs/lessons-learned.md.

Docs
architecture.md — how the lab is laid out and why
ubuntu-server-setup.md — building the SOC server
attacker-setup.md — building the attacker
networking.md — IPs and connectivity testing
lessons-learned.md — everything that broke
Next

Victim VM, then Wazuh on the SOC server, then agents, then start actually generating activity and seeing what gets caught.

Scope

This is a defensive lab. Everything runs against VMs I own on an isolated virtual network. No malware, nothing destructive, nothing pointed at anything outside the lab. 
