# TASK 1:
## Network-Scan-Checklist

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
e.g., 192.168.1.23/24 → network 192.168.1.0/24

Run a TCP SYN + service/version scan and save:
sudo nmap -sS -sV -T4 192.168.1.0/24 -oN scan_results.txt -oX scan_results.xml
xsltproc scan_results.xml -o scan_results.html

Only scan systems/networks you own or have written permission to test. Scanning can trigger alerts and may be against policy for managed networks. Keep logs and get authorization when testing in professional or academic environments.

# TASK 2:
Phishing Email Analysis
Objective
The goal of this project is to identify phishing characteristics in a suspicious email sample and document the findings.

Tools Used
1. Email client or saved .eml file.
2. Free online email header analyzer - MXToolbox Email Header Analyzer

Steps Performed
1. Obtained a sample phishing email (open-source samples available online).  
2. Examined sender's email address for spoofing (lookalike domains).  
3. Checked email headers using an online header analyzer for discrepancies (SPF/DKIM/DMARC failures, suspicious IP).  
4. Identified suspicious links or attachments.  
5. Looked for urgent or threatening language in the email body.  
6. Verified mismatched URLs (hover text vs actual link).  
7. Checked for spelling and grammar errors.  
8. Summarized all phishing traits observed.  

Deliverable
A Phishing Email Analysis Report containing:  
- Sender spoofing details  
- Header authentication results  
- Suspicious/mismatched URLs  
- Use of urgency or threats  
- Spelling/grammar issues  
- Attachment risks  
- Final conclusion  

