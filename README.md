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
