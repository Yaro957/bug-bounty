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








	
