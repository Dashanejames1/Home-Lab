## Home Lab
VMware lab running Kali Linux + Metasploitable 2.

**Lessons learned:**
- Nmap scans hung indefinitely against Metasploitable due to DNS resolution 
  issues on the Host-Only network. Fix: always use `-n` to skip DNS.
  Working command: `sudo nmap -sT -Pn --disable-arp-ping -n -F [target IP]`
  
Why did this happen ? Nmap tried to lookup a DNS name for the target IP before scanning it but the Host-only network has no DNS server to answer that request, which is what caused the "hang"or unresponsiveness.
