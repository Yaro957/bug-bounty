# bug-bounty
full notes of bug bounty
# What Is Reconnaissance?

Reconnaissance is the process of collecting as much information as possible about a target system to find ways to penetrate it. It is an important preparatory phase of security assessments.

Reconnaissance involves a set of processes and techniques:
- Footprinting
- Scanning
- Enumeration

## Types of Reconnaissance

### 1. Passive Reconnaissance
1. Uses passive investigation methods to collect information indirectly.
2. Gathers information about a system or network infrastructure.
3. Takes more time.
4. Is hard to detect.

### 2. Active Reconnaissance
1. Uses active investigation methods to collect information directly.
2. Uses SQL injections to observe errors or system responses.
3. Takes less time.
4. Is easy to detect.

## Before Recon

- Company name
- Available scope
- User credentials to log in (more than one account)
- Overview of the company's business, work, and logic
- Security-related information from the program page

## After Recon

- Subdomains
- ASN and acquisitions
- Service information
- Database information
- Backend technology use
- Information exposure
- Interesting directories and endpoints
- Potentially vulnerable links
- More and more

# What Is Subdomain Enumeration?

Subdomain enumeration is one of the most important parts of the reconnaissance phase.

- Helps widen the scope.
- Reveals subdomains that are within the scope of a security assessment.
- Provides more targets to find vulnerabilities.
- Increases the chances of finding good bugs.

## Tools

- **Knock.py:** https://github.com/guelfoweb/knock
- **Sublist3r:** https://github.com/aboul3la/Sublist3r
- **DNSdumpster:** https://dnsdumpster.com/
- **Netcraft:** https://searchdns.netcraft.com/
- **Crt.sh:** https://crt.sh/
-**assetfinder**
-**amass**

# Knock.py

Knock.py is a Python tool designed to enumerate subdomains of a target domain using a wordlist.

## How to Use Knock.py

1. Download from GitHub: https://github.com/guelfoweb/knock
2. Install all requirements as suggested in the repository.
3. Open it in your console and run it.

# Sublist3r

Sublist3r is a Python tool designed to enumerate website subdomains using OSINT.

## How to Use Sublist3r

1. Download from GitHub: https://github.com/aboul3la/Sublist3r
2. Install all requirements as suggested in the repository.
3. Open it in your console and run it.



# DNSdumpster

DNSdumpster is a free online domain research tool that discovers hosts related to a domain. It helps gather information about the target, such as:

- Subdomains
- HTTP headers
- Banner grabbing
- MX records
- DNS servers
- TXT records

## How to Use DNSdumpster

1. Visit https://dnsdumpster.com/ and enter your target domain.
2. Click the symbols below the subdomain name to view different results.

# Netcraft

Netcraft is an Internet monitoring company that monitors uptime, detects server operating systems, and provides other services. Its online search tool allows users to query databases for host information.

## How to Use Netcraft

1. Visit https://searchdns.netcraft.com/ and enter your target domain using an asterisk, such as `*.url.com`.
2. View the available Netblock, OS, and Site Report information.

## Netblock

A netblock is a range of consecutive IP addresses. Netblocks are sometimes displayed in Classless Inter-Domain Routing (CIDR) notation.


# Sort Subdomains

Remove duplicate subdomains from the collected files.

**Command:**

```bash
sort -u sub.txt sub1.txt sub2.txt >> sorted_subdomain.txt
```

# Filter Out Live Subdomains

Filter out live subdomains using `httpx` and `httprobe`.

### Using httpx

```bash
cat sorted_subdomain.txt | httpx | tee -a httpx_sub.txt
```

### Using httprobe

```bash
cat sorted_subdomain.txt | httprobe | tee -a httprobe_sub.txt
```

# Recommended Tools and Automation Frameworks

## Automation Frameworks

- **3klCon:** https://github.com/eslam3kl/3klCon
  - My own framework based on the above methodology.
- **Bheem:** https://github.com/harsh-bothra/Bheem

## Tools

- **3klector:** https://github.com/eslam3kl/3klector
- **crtfinder:** https://github.com/eslam3kl/crtfinder
- **Subfinder:** https://github.com/projectdiscovery/subfinder
- **Assetfinder:** https://github.com/tomnomnom/assetfinder
- **Altdns:** https://github.com/infosec-au/altdns
- **Dirsearch:** https://github.com/maurosoria/dirsearch
- **Gau:** https://github.com/lc/gau
- **Git-hound:** https://github.com/tillson/git-hound
- **Gf:** https://github.com/tomnomnom/gf
- **Gf-patterns:** https://github.com/1ndianl33t/Gf-Patterns
- **Nuclei:** https://github.com/projectdiscovery/nuclei
- **Nuclei-templates:** https://github.com/projectdiscovery/nuclei-templates
- **Subjack:** https://github.com/haccer/subjack
- **Httpx:** https://github.com/projectdiscovery/httpx
- **Waybackurls:** https://github.com/tomnomnom/waybackurls
- **all.txt:** https://gist.github.com/jhaddix/86a06c5dc309d08580a018c66354a056

# Analysing Web Technologies

We can analyse web technologies using various tools.

## Tools

- Wappalyzer Extension
- Netcraft
- WhatWeb
- Whois
- Reverse IP Domain Check

## Reverse IP Domain Check

A Reverse IP Domain Check takes a domain name or IP address pointing to a web server and searches for other sites known to be hosted on the same web server.

- Data is gathered from search engine results.
- It provides a list of domains hosted on the same server.


# WHOIS

Search the WHOIS database to find domain and IP owner information and other statistics.

# Reverse IP Domain Checker

We will use [YouGetSignal](https://www.yougetsignal.com/) for this.

## How to Use It

1. Go to https://www.yougetsignal.com/ and select **Reverse IP Domain Check**.
2. Enter your target domain and check the results.
3. After collecting domains, subdomains, and their subdomains, find the IP range.
4. A WHOIS lookup allows you to search the public database for information about a specific domain, such as:
   - Expiration date
   - Current registrar
   - Registrant information
   
IP RANGE FINDER
An IP address is always a set of four numbers like that Fach number can range from 0 to 255. So, the full IP
addressing range goes from 0.0. 0.0 to 255.255. 255.255. Finding an IP range in recon is equally important
because it tells us that how many unique IP addresses block a particular domain has.

How to find it ?
1. Go to https://bgp.he.net/ and enter your target IP
2. Click on search and after the result appears click on Whois
3.After we get the range it is mandatory to perform whois check to ensure that the IP belongs to the same target
domain

# What Is Google Dorking?

Google Dorking is the process of using advanced search operators to make searches more precise and focus on specific topics.

## Links

- https://dorks.faisalahmed.me/
- https://infosecwriteups.com/dorking-for-bug-bounties-d81cc857b2c8
- https://www.exploit-db.com/google-hacking-database

# What Is GitHub Dorking?

GitHub Dorking uses specific search keys to find sensitive information in public repositories. It is similar to Google Dorking.

- Manual searching can be better than automation.
- Spend time searching for useful information.
- For automation, use GitDorker.

## Links

- https://github.com/Vaidik-pandya/Github_recon_dorks
- https://github.com/obheda12/GitDorker

  # What Is the Wayback Machine?

The Wayback Machine is a digital archive of the World Wide Web, founded by the Internet Archive. It allows users to go back in time and see what websites looked like in the past.

Using the Wayback Machine can be advantageous because you can check older versions of websites for sensitive files that existed previously.

## Links

- https://web.archive.org/web/*/website.com/*
- https://github.com/tomnomnom/waybackurls

# How to Use the Wayback Machine

1. Go to https://github.com/tomnomnom/waybackurls.
2. Install it using Go.
3. Run the following command:

```bash
cat httpx.txt | waybackurls | tee -a way.txt
```

## Filtering Wayback Machine Results

You can use filters to search the Wayback Machine.

1. Visit https://web.archive.org/web/*/website.com/* to get a list of paths crawled by the Wayback Machine.
2. Use filters to search for specific files.
3. Pass the `waybackurls.txt` file through the `gf` tool and use `gf-patterns` to filter links that may be vulnerable.


# What Is Content Discovery?

Content discovery is the process of finding hidden files, endpoints, and parameters that can be used during further penetration testing.

## Links

- https://github.com/v0re/dirb
- https://github.com/KajanM/DirBuster
- https://github.com/OJ/gobuster

## Some Takeaways

1. Don't rely on a single tool or approach for information gathering. Use at least two tools or approaches and verify the results.
2. Focus more on manual testing than automation.
3. Spend more time on information gathering.


# What Is Parameter Fuzzing?

Fuzzing, or fuzz testing, is the automated process of providing malformed or random data to software to discover bugs.

In penetration testing, a wordlist is typically used to iterate through values, and the results are observed and analyzed.

Fuzzing usually involves testing inputs, which can include:

- Alphanumeric characters to find buffer overflows.
- Odd characters to test for SQL injection.
- Hidden directories and files.
- Valid parameter names and values.

## Links

- https://github.com/ffuf/ffuf
- https://github.com/danielmiessler/SecLists


# FFUF

## Installation

1. Install FFUF by following the steps provided here: https://github.com/ffuf/ffuf
2. Download SecLists for wordlists: https://github.com/danielmiessler/SecLists

## Directory Discovery

1. Take the subdomains text file and pass it through Dirsearch or FFUF to discover hidden directories and files, such as `http://url.com/database_conf.txt`.
2. Filter the results to show only `2xx`, `3xx`, and `403` response codes using the tool's options (`-h` to view available filters).
3. Collect the results in a text file named `hidden_directories.txt`.
4. Check the results for data leakage or forbidden pages and try to bypass them.

## References

- https://null-byte.wonderhowto.com/how-to/fuzz-parameters-directories-more-with-ffuf-0330806/
- https://gist.github.com/jhaddix/b80ea67d85c13206125806f0828f4d10

# What Is Shodan?

Shodan is a search engine that allows users to find specific types of computers connected to the internet using various filters.

It is also described as a search engine for service banners, which are metadata sent by a server back to the client.

## Links

- https://www.shodan.io/
- https://securitytrails.com/blog/top-shodan-dorks
- https://github.com/daffainfo/AllAboutBugBounty/blob/master/Recon/Shodan%20Dorks.md
- https://medium.com/@sw33tlie/finding-a-p1-in-one-minute-with-shodan-io-rce-735e08123f52

# What Is URL and Parameter Discovery?

The easiest active way to discover URLs and their corresponding parameters on a target is to crawl the website.

## Links

- https://github.com/devanshbatham/ParamSpider
- https://github.com/jaeles-project/gospider
- https://github.com/s0md3v/Arjun
- https://github.com/tomnomnom/qsreplace
- https://github.com/lc/gau

# Parameter Discovery Tools

## 1. ParamSpider

Finds parameters from web archives of the entered domain and its subdomains.

## 2. Gospider

A fast web spider written in Go.

## 3. Arjun

Web applications use parameters (or queries) to accept user input.

We want to find as many parameters as possible, which we can later scan or review manually. That's where Arjun comes in.

# Parameter Discovery Tools

## 1. ParamSpider

Finds parameters from web archives of the entered domain and its subdomains.

## 2. Gospider

A fast web spider written in Go.

## 3. Arjun

Web applications use parameters (or queries) to accept user input.

We want to find as many parameters as possible, which we can later scan or review manually. That's where Arjun comes in.

## 4. GAU (GetAllUrls)

Fetches known URLs from:
- AlienVault's Open Threat Exchange
- Wayback Machine
- Common Crawl

Inspired by Tomnomnom's `waybackurls`.

## 5. QSReplace

Removes duplicate URLs and parameter combinations.

# What Is Network Scanning?

Network scanning refers to the process of obtaining additional information and performing more detailed reconnaissance based on the information collected during the footprinting phase.

## Objectives of Network Scanning

- Discover live hosts, IP addresses, and open ports.
- Discover OS and system architecture.
- Discover services running on hosts.
- Discover vulnerabilities running on hosts.

## Links

- https://github.com/nmap/nmap
- https://github.com/robertdavidgraham/masscan

# Nmap

Nmap (https://nmap.org/) is a powerful port scanner and service enumerator with vulnerability scanning capabilities.

Nmap has two main features:

1. It allows you to detect ports and services where potential vulnerabilities may exist.
2. It has an extensive scripting language called **Nmap Scripting Engine (NSE)**, which allows scripts to automate tasks.

Nmap is used for network discovery and security auditing.

In short, Nmap displays exposed services on a target machine along with useful information such as version and OS detection.

It is also open-source!

# TCP Connect Scan

TCP Connect scan completes the TCP three-way handshake.

- If a port is open, the operating system completes the TCP three-way handshake.
- The port scanner immediately closes the connection to avoid DoS.
- This scan is noisy because services can log the sender's IP address and may trigger Intrusion Detection Systems (IDS).

# UDP Scan

This scan checks whether any UDP ports are listening.

- UDP does not respond with a positive acknowledgment like TCP.
- It only responds to an incoming UDP packet when the port is closed.
- This scan can sometimes show false positives.
- It can reveal Trojan horses running on high UDP ports and hidden RPC services.
- It may be quite slow because some machines intentionally slow down responses to avoid being overwhelmed.
- Windows machines do not implement this slowdown feature, so UDP scans can be performed on Windows hosts normally.

# SYN Scan

SYN scan is another form of TCP scanning.

- Instead of using the operating system's network functions, the port scanner generates raw IP packets and monitors responses.
- It is also known as **Half-Open Scanning** because it never opens a full TCP connection.
- The port scanner generates a SYN packet.
- If the target port is open, it responds with a SYN-ACK packet.
- The scanner responds with an RST packet, closing the connection before the handshake is completed.
- If the port is closed but unfiltered, the target responds with an RST packet.

There is debate over which scan is less intrusive on the target host.

**Advantage:** Individual services never actually receive a completed connection.

# FIN Scan

- FIN scan is a stealthy scan, similar to SYN scan, but sends a TCP FIN packet instead.
- Most, but not all, computers send an RST packet in response.
- FIN scans can show false positives and negatives.
- They may get under the radar of some IDS programs and other countermeasures.

# ACK Scan

ACK scanning determines whether a port is filtered or not.

- It is useful when attempting to identify the existence of a firewall and its rulesets.
- Simple packet filtering allows established connections (packets with the ACK bit set).
- A more sophisticated stateful firewall might not allow them.

# NULL Scan

- A stealthy scan that sets all TCP header flags to off or null.
- This is not normally a valid packet, and some hosts may not know what to do with it.
- Windows operating systems are in this group, so NULL scans against them produce unreliable results.
- For non-Windows servers protected by a firewall, this can be a way to get through.

# XMAS Scan

- Similar to the NULL scan, except all flags in the TCP header are set to on.
- Windows machines won't respond to this due to the way their TCP stack is implemented.
- XMAS scans derive their name from the flags turned on within a packet.
- These scans manipulate the PSH, URG, and FIN flags of the TCP header.

# IDLE Scan

- A super stealthy method in which scan packets are bounced off an external host.
- You don't need control over the other host, but it must meet certain requirements.
- You must input the IP address of the "zombie" host and the port number to use.
- It is one of the more controversial options in Nmap since it mainly has a use for malicious attacks.


# RPC Scan

- This special type of scan looks for machines responding to RPC (Remote Procedure Call) services.
- RPC allows remote commands to be run on a machine under certain conditions.
- It can be a dangerous service.
- Since RPC services can run on many different ports, it is difficult to identify them through a normal scan.
- This scan probes the ports found open on a machine to identify the program name and version if RPC is running.
- It is useful to run these scans periodically to identify if and where RPC services are running.

	# Nmap Scan Techniques

| Switch | Description | Example |
|---|---|---|
| `-sS` | TCP SYN port scan | `nmap -sS 192.168.1.1` |
| `-sT` | TCP Connect port scan | `nmap -sT 192.168.1.1` |
| `-sU` | UDP port scan | `nmap -sU 192.168.1.1` |
| `-sA` | TCP ACK port scan | `nmap -sA 192.168.1.1` |

# Nmap Host Discovery

| Switch | Description | Example |
|---|---|---|
| `-Pn` | Only port scan. | `nmap -Pn 192.168.1.1` |
| `-sn` | Only host discovery. | `nmap -sn 192.168.1.1` |
| `-n` | Disable DNS resolution. | `nmap -n 192.168.1.1` |
| `-PR` | ARP discovery on local network. | `nmap -PR 192.168.1.1` |

# Nmap Port Specification

| Switch | Description | Example |
|---|---|---|
| `-p` | Specify a port or port range. | `nmap -p 22-80 192.168.1.1` |
| `-p-` | Scan all ports. | `nmap -p- 192.168.1.1` |
| `-F` | Fast port scan (top 100 ports). | `nmap -F 192.168.1.1` |


# Nmap Service and Version Detection

| Switch | Description | Example |
|---|---|---|
| `-sV` | Detect the version of services. | `nmap -sV 192.168.1.1` |
| `-A` | Enable OS detection, version detection, script scanning, and traceroute. | `nmap -A 192.168.1.1` |

# Nmap Timing and Performance

| Switch | Description | Example |
|---|---|---|
| `-T0` | Paranoid IDS evasion. | `nmap -T0 192.168.1.1` |
| `-T1` | Sneaky IDS evasion. | `nmap -T1 192.168.1.1` |
| `-T2` | Polite IDS evasion (requires less bandwidth). | `nmap -T2 192.168.1.1` |
| `-T3` | Normal IDS evasion (default). | `nmap -T3 192.168.1.1` |
| `-T4` | Aggressive speed scan (requires fast network). | `nmap -T4 192.168.1.1` |
| `-T5` | Insane speed scan (requires massive network speed). | `nmap -T5 192.168.1.1` |


# Nmap NSE Scripts

| Switch | Description | Example |
|---|---|---|
| `-sC` | Default script scan. | `nmap -sC 192.168.1.1` |
| `--script banner` | Specify a single script (banner grabbing). | `nmap --script banner 192.168.1.1` |

# Nmap Firewall / IDS Evasion

| Switch | Description | Example |
|---|---|---|
| `-f` | Use fragmented IP packets (packet filter evasion). | `nmap -f 192.168.1.1` |
| `-D` | Decoy scan (spoofed source IPs). | `nmap -D 192.168.1.1` |
| `-g` | Use the given source port number. | `nmap -g 22 192.168.1.1` |


# Nmap Script Engine (NSE)

One of the interesting features of Nmap is the Nmap Script Engine (NSE), which provides more flexibility and efficiency.

It allows you to write your own scripts using the Lua programming language and share them with other Nmap users.

## Types of NSE Scripts

There are four types of NSE scripts:

### 1. Prerule Scripts
- Run before any of Nmap's scan operations.
- Executed when Nmap hasn't gathered any information about a target yet.

### 2. Host Scripts
- Run after Nmap performs normal operations such as host discovery, port scanning, version detection, and OS detection against a target host.

### 3. Service Scripts
- Run against specific services listening on a target host.

### 4. Postrule Scripts
- Run after Nmap has scanned all of its target hosts.

# Nmap NSE Scripts

## Location of NSE Scripts

To see the location of all available NSE scripts, navigate to:

```bash
cd /usr/share/nmap/scripts
```

## Loading NSE Scripts

NSE scripts are loaded using the `--script` flag.

It allows you to run scripts by providing:
- Categories
- Script file names
- Directories containing scripts

### Syntax

```bash
nmap -sC target
```

Loads the default scripts.

# Nmap NSE Script Options

## Script Help and Arguments

- Use the `--script-help` option to view a script's description.
- Use `--script-args` to pass arguments to scripts.
- Use `--script-args-file` to provide a filename containing script arguments instead of passing them through the command line.

## Running Default NSE Scripts

To perform a scan with most of the default scripts, use the `-sC` flag or `--script=default`.

**Commands:**

```bash
nmap -sC scanme.nmap.org
```

**OR**

```bash
nmap --script=default scanme.nmap.org
```

**OR**

```bash
nmap --script default scanme.nmap.org
```

# Recommended Tools and Automation Frameworks

## Automation Frameworks

- **3klCon:** https://github.com/eslam3kl/3klCon
  - My own framework based on the above methodology.
- **Bheem:** https://github.com/harsh-bothra/Bheem

## Tools

- **3klector:** https://github.com/eslam3kl/3klector
- **crtfinder:** https://github.com/eslam3kl/crtfinder
- **Subfinder:** https://github.com/projectdiscovery/subfinder
- **Assetfinder:** https://github.com/tomnomnom/assetfinder
- **Altdns:** https://github.com/infosec-au/altdns
- **Dirsearch:** https://github.com/maurosoria/dirsearch

# Recommended Tools

- **Gau:** https://github.com/lc/gau
- **Git-hound:** https://github.com/tillson/git-hound
- **Gf:** https://github.com/tomnomnom/gf
- **Gf-patterns:** https://github.com/1ndianl33t/Gf-Patterns
- **Nuclei:** https://github.com/projectdiscovery/nuclei
- **Nuclei-templates:** https://github.com/projectdiscovery/nuclei-templates
- **Subjack:** https://github.com/haccer/subjack
- **Httpx:** https://github.com/projectdiscovery/httpx
- **Waybackurls:** https://github.com/tomnomnom/waybackurls
- **all.txt:** https://gist.github.com/jhaddix/86a06c5dc309d08580a018c66354a056


# Recommended Tools

- **Gau:** https://github.com/lc/gau
- **Git-hound:** https://github.com/tillson/git-hound
- **Gf:** https://github.com/tomnomnom/gf
- **Gf-patterns:** https://github.com/1ndianl33t/Gf-Patterns
- **Nuclei:** https://github.com/projectdiscovery/nuclei
- **Nuclei-templates:** https://github.com/projectdiscovery/nuclei-templates
- **Subjack:** https://github.com/haccer/subjack
- **Httpx:** https://github.com/projectdiscovery/httpx
- **Waybackurls:** https://github.com/tomnomnom/waybackurls
- **all.txt:** https://gist.github.com/jhaddix/86a06c5dc309d08580a018c66354a056


# Further Resources and Tools

## 1. Broken URL Checker

- **Burl:** https://github.com/tomnomnom/burl

## 2. Fetch Multiple Paths

Fetch many paths for multiple hosts without overwhelming the hosts.

- **Meg:** https://github.com/tomnomnom/meg

## 3. Concurrent HTTP Requests

Make concurrent requests using the curl command-line tool.

- **ConcURL:** https://github.com/tomnomnom/concurl

## 4. APK Endpoint Extraction

Extract endpoints from APK files.

- **APKURLGrep:** https://github.com/ndelphit/apkurlgrep

## 5. XSS Scanning

- **kxss:** https://github.com/tomnomnom/hacks/tree/master/kxss
- **DalFox:** Finder of XSS; parameter analysis and XSS scanning tool based on Go.
  - https://github.com/hahwul/dalfox

## 6. Subdomain Enumeration

- **ShuffleDNS:** A wrapper around MassDNS written in Go that allows you to enumerate valid subdomains using active brute force, resolve subdomains with wildcard handling, and provides input-output support.
  - https://github.com/projectdiscovery/shuffledns

- **Fast Subdomain Enumeration Tool:** For penetration testers.

## 7. Web Path Scanning

- **Dirsearch:** https://github.com/maurosoria/dirsearch

## 8. Directory/File, DNS and VHost Busting

- **Gobuster:** A tool written in Go.
  - https://github.com/OJ/gobuster

## 9. Web Application Fuzzer

- **Wfuzz:** https://github.com/xmendez/wfuzz/

## 10. DNS Recon and Research

Find and look up DNS records.

- **DNSdumpster:** https://dnsdumpster.com/

  # Further Resources and Tools

## Subdomain Enumeration

- **Sublist3r:** https://github.com/aboul3la/Sublist3r
- **Knock Subdomain Scan:** https://github.com/guelfoweb/knock

## SPF Record Analysis

A Python script to parse netblocks and domain names from SPF records.

- https://github.com/0xbharath/assets-from-spf/

## JavaScript File Discovery

A tool to quickly get all JavaScript sources/files.

- https://github.com/003random/getJS

## Internet-Wide Scan Data

Project Sonar provides open access to data for researchers and community members. It conducts internet-wide surveys to gain insights into global exposure to common vulnerabilities.

- https://opendata.rapid7.com/

## Wordlists

- **SecLists:** https://github.com/danielmiessler/SecLists

## Useful Search Engines

- **Shodan Facet:** https://beta.shodan.io/search/facet?query=port%3A443&facet=ssl.version
- **GreyNoise:** https://viz.greynoise.io/
- **ZoomEye:** https://www.zoomeye.org/
- **FOFA:** https://fofa.so/
- **ONYPHE:** https://onyphe.io/
- **Hunter:** https://hunter.io/
- **BinaryEdge:** http://binaryedge.io/



# What Is Visual Recon?

After compiling a list of HTTP-enabled targets, we want to identify which web services are running on these hosts.

One of the first steps is to visit and inspect the websites.

The easiest and fastest way to do this for multiple targets is to perform automated screenshotting of all targets.

## Links

- https://github.com/FortyNorthSecurity/EyeWitness


# EyeWitness

EyeWitness is designed to take screenshots of websites, provide server header information, and identify default credentials (if known).

## Commands

**1. Scan URLs from a text file**

```bash
./EyeWitness -f urls.txt --web
```

**2. Scan URLs from an XML file**

```bash
./EyeWitness -x urls.xml --timeout 8
```

**3. Scan using a SOCKS5 proxy**

```bash
./EyeWitness.py -f urls.txt --web --proxy-ip 127.0.0.1 --proxy-port 8080 --proxy-type socks5 --timeout 120
```

# WebScreenshot

A simple script to take screenshots of a list of websites, based on the URL-to-Image PhantomJS script.

## Installation

```bash
git clone https://github.com/maaaaz/webscreenshot.git
```

## Usage

```bash
python webscreenshot.py -i list.txt -w 40
```

# Find All JavaScript Files

JavaScript files are always worth examining. Filter URLs that return JavaScript files and save them in a separate file for later analysis.

## Command

```bash
cat urls.txt | grep ".js" > js-urls.txt
```

## Reference

https://blog.appsecco.com/static-analysis-of-client-side-javascript-for-pen-testers-and-bug-bounty-hunters-f1cb1a5d5288?gi=e19a920a2344



# LinkFinder

LinkFinder is a Python script that finds endpoints in JavaScript files.

## Installation

```bash
git clone https://github.com/GerbenJavado/LinkFinder.git
cd LinkFinder
python setup.py install
pip3 install -r requirements.txt
```

## Usage

```bash
python linkfinder.py -i https://example.com/1.js -o results.html
```

## Link

https://github.com/GerbenJavado/LinkFinder



# What Is Content Discovery?

Content discovery is the process of finding hidden files, endpoints, and parameters that can be used during further penetration testing.

## Links

- https://github.com/vOre/dirb
- https://github.com/KajanM/DirBuster
- https://github.com/OJ/gobuster

## Some Takeaways

1. Don't rely on a single tool or approach for information gathering. Use at least two tools or approaches and verify the results.
2. Focus more on manual testing than automation.
3. Spend more time on information gathering.
