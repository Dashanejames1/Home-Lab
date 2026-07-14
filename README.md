## Home Lab
VMware lab running Kali Linux + Metasploitable 2.

**Lessons learned:**
- Nmap scans hung indefinitely against Metasploitable due to DNS resolution 
  issues on the Host-Only network. Fix: always use `-n` to skip DNS.
  Working command: `sudo nmap -sT -Pn --disable-arp-ping -n -F [target IP]`
