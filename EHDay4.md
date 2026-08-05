# How does an ethical hacker begin investigating a target?

It’s an intermediate, practical, conceptual guide on using scanning tool Nmap to collect essential information before exploiting a target.

![EHDay4_Cover](./images/EHDay4_Cover.png)

Welcome to Day 4 of our Ethical Hacking Journal.

Suppose you are hired by a company to perform penetration tests on their web application. You have all the written permission you need, but where do you even start it? You wouldn’t immediately start exploit a web application. Instead, you first gather essential information about that target. That’s where tools like Nmap come into play.

>The more you understand your target, the fewer assumptions you need to make.

If you did like to get hands-on practice, you’ll need:

- A computer installed Linux [Guide is [HERE](https://github.com/Tech-FireFish/Ethical-Hacking-Blog/blob/main/Day1.md)]
- Namp
Install Nmap with `sudo apt install nmap` in your Linux terminal.

**Ethics Reminder/Disclaimer**: The information provided in this text below is intended solely for educational and ethical purposes. It is crucial to emphasize that the tool Namp should only be studied and applied in legal, responsible, and authorized contexts.

Here is a legal website to test: scanme.nmap.org

Let’s dive in now. 😄

**Legal Boundaries in Penetration test[Conceptual]**
The most important rule in penetration testing is authorization. Only scan systems you own or have explicit written permission to test. Scanning third-party networks without authorization may be interpreted as unauthorized access or hostile reconnaissance, depending on the jurisdiction.

- United States: The Computer Fraud and Abuse Act (CFAA)
- United Kingdom: The Computer Misuse Act 1990
- European Union: Many member states treat unauthorized network scanning or mapping as violations of national cybercrime laws implementing EU directives.

Potential consequences include:

- Criminal penalties ranging from fines to multiple years of imprisonment, depending on the offense and resulting damage.
- Civil liability for investigation, incident response, system recovery, and security audit costs, which can easily exceed thousands of dollars.

Rule of thumb: If you do not own the system or lack explicit written authorization, do not scan it.

**Nmap Commands[Practical]**
Imagine you’re a detective investigating a building. Before breaking into the building, you might simply observe what is exposed first.

During penetration tests, each IP address represents a computer on the network. However, the IP address itself is not the target to exploit, but the infrastructure that is built on it. These infrastructures include components like different opening ports, protocols used and services used to build it.

Here a great analogy:

- Think of an IP address as the street address of a building.
- Ports become individual doors.
- Services become the businesses operating behind those doors.

In other words, you want to know the infrastructure of your target computer first before exploitation because those components are the actual targets of your penetration test.

![EHDay4_Figure2.1](./images/EHDay4_Figure2.1.png)

Suppose you are testing scanme.nmap.org(legal website to test), you can run:

```
# Determine the state and service of a specific IP address.
nmap [website_name/IP address]
# e.g. nmap scanme.nmap.org

# OUTPUT:
# Nmap scan report for scanme.nmap.org (45.33.32.156)
# Host is up (0.026s latency).
# Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
# Not shown: 95 filtered tcp ports (no-response)
# PORT    STATE SERVICE
# 22/tcp  open  ssh
# 25/tcp  open  smtp
# 80/tcp  open  http
# 110/tcp open  pop3
# 143/tcp open  imap
```

to send a special crafted packet to the target IP address to determine the state and services run in the target host.

In actual practice, the time required for scanning can be boredly long. However, we can add this combination of options to speed up the process by only doing the essential work: `-T4 -F -n`.

Specifically,

- `-F` instructs the nmap tool to scan only the top 100 common ports on the target host, rather than scanning 1000+ ports.
- `-n` instructs the nmap tool to skip the reverse DNS queries. (Skip determining the domain name of the target host)
- `-T4` instructs the nmap tool to increase speed limits, parallelism, and lower timeout waits.

>Reconnaissance doesn’t tell you how to exploit a target. It tells you where to focus your investigation.

The missing part of the previous command is that no services are revealed. That is essential for our information gathering, you can run:

```
# Determine the versions of those services of a specific IP address
nmap -sV [IP address/Domain Name]
# e.g. nmap -sV -F -n -T4 scanme.nmap.org

# OUTPUT:
# Nmap scan report for scanme.nmap.org (45.33.32.156)
# Host is up (0.032s latency).
# Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
# Not shown: 98 filtered tcp ports (no-response)
# PORT   STATE SERVICE VERSION
# 22/tcp open  ssh     OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
# 80/tcp open  http    Apache httpd 2.4.7 ((Ubuntu))
# Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

For those who wandering the operating system and device type of their target computer, you can run:

```
# Determine the operating system and device
nmap -O [IP Address/Domain Name]
# e.g. nmap -O scanme.nmap.org

# OUTPUT:
# Nmap scan report for scanme.nmap.org (45.33.32.156)
# Host is up (0.046s latency).
# Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
# Not shown: 98 filtered tcp ports (no-response)
# PORT   STATE SERVICE
# 22/tcp open  ssh
# 80/tcp open  http
# Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
# Device type: VoIP adapter|bridge|general purpose
# Running (JUST GUESSING): AT&T embedded (93%), Oracle Virtualbox (92%), Slirp (92%), QEMU (90%)
# OS CPE: cpe:/o:oracle:virtualbox cpe:/a:danny_gasparovski:slirp cpe:/a:qemu:qemu
# Aggressive OS guesses: AT&T BGW210 voice gateway (93%), Oracle Virtualbox Slirp NAT bridge (92%), QEMU user mode network gateway (90%)
# No exact OS matches for host (test conditions non-ideal).
-O is the letter O not number 0.
```

to identify their operating system and device.

Furthermore, you can gather their configuration information on opening ports by running:

```
# Gather extra informations
nmap -sC [IP Address/Domain Name]
# e.g. nmap -sC scanme.nmap.org

# OUTPUT:
# Nmap scan report for scanme.nmap.org (45.33.32.156)
# Host is up (0.036s latency).
# Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
# Not shown: 994 filtered tcp ports (no-response)
# PORT      STATE  SERVICE
# 22/tcp    open   ssh
# | ssh-hostkey: 
# |   1024 ac:00:a0:1a:82:ff:cc:55:99:dc:67:2b:34:97:6b:75 (DSA)
# |   2048 20:3d:2d:44:62:2a:b0:5a:9d:b5:b3:05:14:c2:a6:b2 (RSA)
# |   256 96:02:bb:5e:57:54:1c:4e:45:2f:56:4c:4a:24:b2:57 (ECDSA)
# |_  256 33:fa:91:0f:e0:e1:7b:1f:6d:05:a2:b0:f1:54:41:56 (ED25519)
# 80/tcp    open   http
# |_http-title: Go ahead and ScanMe!
# |_http-favicon: Nmap Project
# 88/tcp    closed kerberos-sec
# 6346/tcp  closed gnutella
# 9929/tcp  open   nping-echo
# 31337/tcp open   Elite
An SSH host key is a cryptographic key pair (a public key and a private key) used by an SSH (Secure Shell) server to identify itself to connecting clients.
```

Once you’re comfortable with the individual options, Nmap provides an all-in-one option:

Option `-A` can run four options at the same time:

- `-O` attempts to identify the operating system of the target.
- `-sV` Identifies exact applications running on the open ports.
- `-sC` runs the default Namp Scripting Engine(NSE) scripts to check for misconfigurations, basic vulnerabilities, and extra information.
- `— traceroutetraces` the network path to the target host to show the network hops in between.
Congratulations. You made it all the way here. 😄

**Credits**
- Tech-FireFish, Contributor, Profile URL

- Machine Learning Specialization instructed by Andrew Ng, Geoff Ladwig, Eddy Shyu, and Aarti Bagul on Coursera platform, 2012, URL.
