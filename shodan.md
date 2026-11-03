# What Is Shodan?

Shodan is a search engine that allows users to discover and access information about devices and services connected to the internet.

It is often referred to as a **"search engine for hackers"** because it specializes in indexing and providing information about internet-connected devices that may be vulnerable to attacks or have misconfigurations.

Unlike traditional search engines that focus on indexing web pages, Shodan scans and indexes various types of devices, including:

- Webcams
- Routers
- Servers
- IoT devices
- And more

By collecting data from these devices, Shodan provides a comprehensive view of the global internet landscape.

It is a valuable tool for:

- Security researchers
- System administrators
- Individuals interested in exploring internet-connected devices.

  # Key Features of Shodan

## 1. Search Filters

Shodan offers advanced search filters that allow users to refine queries based on specific criteria, such as:

- Country
- City
- Port
- Operating system
- And more

This enables targeted searches for devices or services of interest.

## 2. Banner Information

Shodan extracts banner information from devices, which includes:

- Device details
- Software version
- Open ports
- Other relevant information

This helps identify specific devices or services that meet certain criteria.

## 3. Exploits and Vulnerabilities

Shodan integrates information about known exploits and vulnerabilities, providing insights into potentially insecure devices or services.

# Basic Dorks

Start with simple dorks to narrow down your search.

## Examples

- `port:80` — Find devices with port 80 open (HTTP).
- `country:"United States"` — Search for devices in a specific country.
- `hostname:example.com` — Find devices associated with a particular hostname.


# Negation Operator

Use the `-` operator to exclude specific criteria from your search.

## Example

```text
port:80 -country:"United States"
```

Find HTTP servers while excluding those located in the United States.

# Range Operators

Use range operators to specify a range of values.

## Examples

- `port:1000-2000` — Search for devices with ports between 1000 and 2000.
- `net:192.168.0.0/24` — Find devices within a specific IP address range.



# Banners and Keywords

Include specific keywords or banners to narrow down your search.

## Examples

- `apache` — Find devices running the Apache web server.
- `title:"Security Camera"` — Search for web interfaces associated with security cameras.



# Advanced Operators

Shodan provides advanced operators to refine your search further.

## Examples

- `os:Linux` — Find devices running the Linux operating system.
- `city:"New York"` — Search for devices in a specific city.
- `product:"Elasticsearch"` — Find devices running Elasticsearch.



# Shodan Exploits

Use the `has_exploit` operator to search for devices vulnerable to specific exploits.

## Example

- `has_exploit:cve-2019-0708` — Find devices vulnerable to the BlueKeep vulnerability.




# Shodan Dorks

## Resources

- [Shodan Dorks – Bug Bounty Wordlists](https://github.com/Karanxa/Bug-Bounty-Wordlists/blob/main/shodan-dorks.txt)
- [Shodan Dorks – humblelad](https://github.com/humblelad/Shodan-Dorks)

