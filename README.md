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


	
