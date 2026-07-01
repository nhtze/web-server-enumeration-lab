## Environment
Ubuntu Server hosted in VirtualBox using Bridged Networking.
Apache2 was installed and verified using:

sudo apt install apache2
sudo systemctl status apache2

## Reconnaissance
The target was scanned using:

nmap -sT -Pn 192.168.1.153

Open services identified:
22/tcp
80/tcp

## Service Enumeration
Version Detection

nmap -sV -Pn 192.168.1.153

## HTTP Enumeration
Initially, all HTTP NSE scripts were executed.

nmap --script "http-*"

The wildcard executed a large collection of scripts including crawler, brute-force and vulnerability scripts, resulting in long execution times.
The methodology was refined by selecting only the required enumeration scripts.

nmap --script http-title,http-headers,http-methods,http-enum

This approach reduced execution time while producing the desired reconnaissance information.
