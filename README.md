Network-Scan-Checklist

What this repo contains
A short step-by-step checklist (commands + purpose) to: install Nmap, discover your local CIDR, run a SYN scan, save results (text/XML/HTML).
Example commands you can copy-paste into a terminal.

A short remediation & legal notes section.

Prerequisites
A Unix-like system (Kali) or Windows with Nmap installed.
Administrative/root privileges for SYN scans and packet capture.
Permission to scan the target network.

Install Nmap:
sudo apt update
sudo apt install nmap xsltproc tcpdump
nmap --version

Find your local IP/CIDR:
ip -4 addr show scope global | awk '/inet /{print $2}'
# e.g., 192.168.1.23/24 → network 192.168.1.0/24

Run a TCP SYN + service/version scan and save:
sudo nmap -sS -sV -T4 192.168.1.0/24 -oN scan_results.txt -oX scan_results.xml
xsltproc scan_results.xml -o scan_results.html





Only scan systems/networks you own or have written permission to test. Scanning can trigger alerts and may be against policy for managed networks. Keep logs and get authorization when testing in professional or academic environments.
