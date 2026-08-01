# Must Know Commands To Build Your Security Defense.

It’s an intermediate, practical guide on securing Kali Linux. Ethical Hacking Day 3

![EHDay3_Cover_Page](./images/EHDay3_Cover.png)

Welcome to Day 3 of our Ethical Hacking Journal: Kali Linux Security Hardening | Part II

Nobody likes their property getting stolen. We lock our doors, build fences, and even install cameras to discourage the intruders. Cybersecurity follows the same idea. Instead of protecting a house, we protect our computers and network with a strong password, firewall, and other defensive tools.

>Every open port is another door worth protecting.

**Note:** You can view the previous blog to learn more about security hardenging in [HERE](https://github.com/Tech-FireFish/Ethical-Hacking-Blog/blob/main/EHDay2.md).

## Disable services that are not in use.

Every unnecessary running service increases the attack surface.

Imagine you never use Bluetooth to connect anything. If Bluetooth remains active, it can potentially create unnecessary opportunities for malicious attempts on the software that can contain vulnerabilities. Disabling these unused services like Bluetooth reduces the opportunities a threat actor has to compromise your system.

You can use:

```
# Checks the enabled services
systemctl list-unit-files | grep enabled
# Output: 
# tpm-udev.path                                enabled         enabled
# accounts-daemon.service                      enabled         enabled
```

to filter services that are “enabled”. Here `systemctl` is the primary command used to manage services in Linux systems that use systemd, `list-unit-files` is its option, |peppline instructs that the output of the previous command will be the input for the next command, and `grep enabled` filters output with the keyword “enabled”.

Some services are enabled automatically(static state), while others are only started when needed. For today’s lesson, we’ll focus on services that are enabled at startup(generated state).

You can check the state of a specific service by doing:

```
# Checks the state of a specific service
systemctl status [service_name]
# e.g. systemclt status bluetooth
# Output:
# bluetooth.service - Bluetooth service
     # Loaded: loaded (/usr/lib/systemd/system/bluetooth.service; disabled; pr>
     # Active: inactive (dead)
     # Docs: man:bluetoothd(8)
```

For example, checking the status of a bluetooth service will be `systemctl status bluetooth`. However, if you want to check if a specific service is active currently, do `systemctl is-active [service_name]`.

As you might raise questions on how to know which services are unused or vulnerable. Well, that’s a big question, requiring you to do research on your own. For examples:

- Bluetooth : If you never use any bluetooth devices.
- SSH : If you never remotely log into a computer.
- CUPS : If you never use a printer to print.

The functional meaning of enabling and disabling is that whether or not a specific service will be enabled once a computer is booted up. The function of enabling and disabling a specific service is similar to its literal description.

You can use:

```
# Enables a specific service
sudo systemctl enable [service_name]
# e.g sudo systemctl enable bluetooth
# Outputs:
# Created symlink '/etc/systemd/system/dbus-org.bluez.service' → '/usr/lib/systemd/system/bluetooth.service'.
# Created symlink '/etc/systemd/system/bluetooth.target.wants/bluetooth.service' → '/usr/lib/systemd/system/bluetooth.service'.
```

to enable a specific service. On the other hand, you can replace the “enable” with a “disable” to disable a specific service: `sudo systemctl disable [service_name]`.

Most importantly, `sudo systemctl enable/disable [service_name]` modify boot start-up, while `sudo systemctl start/stop [service_name]` modify the current application state.

For Example:

```
# Start a specific service
sudo systemctl start/stop [service_name]
# e.g sudo systemctl start bluetooth
```

## Configure a firewall

During penetration testing, defenders use firewalls to restrict access.

UFW stands for uncomplicated firewall, it’s a tool that simplifies the process of managing a firewall. We started with installing a tool called UFW by running `sudo apt install ufw` to install the ufw.

Next, you can turn on the ufw by running `sudo ufw enable` to enable the service. You can trun off the ufw by running `sudo ufw disable`. You can check the status by running `sudo ufw status` to check the state of the ufw service.

Specifically, experienced Linux users often run

```
# Checks the Status and Configurations
sudo ufw status verbose
# Outputs:
# Status: active
# Logging: on (low)
# Default: deny (incoming), allow (outgoing), disabled (routed)
# New profiles: skip
```

to check the state of ufw, and furthermore, list the configuration details for your firewall.

Now let’s configure the firewall: Configuration. One practical command to run `sudo ufw default deny incoming` to block all requests initiated by other computers, such as malicious login attempts initiated by threat actors. Specifically, this command will not block any “response” to your request when you visit a webpage or make remote connections.

>Think of this as locking your front door. Visitors cannot enter unless you explicitly unlock the door for them.

A similar command is `sudo ufw default allow outgoing`.This is a command you don’t want to mess up with because denying “outgoing” means you CAN NOT request anything.(You will not be able to open a webpage)

Specifically, if you want to configure your firewall more strictly. You can run:

```
# Allow apecific destination port number and or protocol to pass through.
sudo ufw allow [port_number/protocol]
# e.g. sudo ufw allow 22/tcp
# Outputs:
# Rule added
# Rule added (v6)
# If you run `sudo ufw status verbose` again, you will see:
# New profiles: skip
# To                         Action      From
# --                         ------      ----
# 22/tcp                     ALLOW IN    Anywhere                  
# 22/tcp (v6)                ALLOW IN    Anywhere (v6)    
```

to overwrite the global configuration such as deny incoming and allow outgoing. On the other hand, you can run `sudo ufw deny [port_number/protocol]` to deny requests that have your specified port number as their destination, while specifying the protocol remain optional.

Security Tools Chart
Professional defenders rarely rely on only one security tool.

UFW is only one piece of the puzzle. Below are several other popular tools used by cybersecurity professionals.

| Tool | Interface | Purpose |
| :--- | :-------: | :------ |
| **Snort** | Command Line | Intrusion Detection System (IDS) for monitoring and analyzing network traffic. |
| **Suricata** | Command Line | High-performance IDS/IPS for real-time network monitoring and threat detection. |
| **iptables** | Command Line | Firewall tool for configuring rules to filter and manage network traffic. |
| **ClamAV** | Command Line | Antivirus toolkit for scanning and detecting malware. |
| **OSSEC** | Command Line | Host-based Intrusion Detection System (HIDS) for monitoring logs, file integrity, and detecting rootkits. |
| **firewalld** | Command Line | Dynamic firewall management tool that supports network zones and runtime rule changes. |
| **Chkrootkit** | Command Line | Lightweight tool for detecting rootkits and malicious software. |
| **FTester** | Command Line | Tests firewall filtering policies and IDS capabilities through simulated attacks. |
| **Zeek** | Command Line | Network analysis framework for deep packet inspection and protocol analysis. |
| **pfSense** | GUI | Open-source firewall and router platform with advanced networking and security features. |
| **IPFire** | GUI | Modular firewall distribution with built-in IDS, VPN, and network security capabilities. |
| **Uncomplicated Firewall (UFW)** | Command Line | Simplified firewall management tool for Linux systems. |
| **Rootkit Hunter (rkhunter)** | Command Line | Scans for rootkits, backdoors, and known local exploits. |

**Congratulations. You made it all the way here.** 😄

# Credits

- Tech-FireFish, Contributor, [Profile_URL](https://github.com/Tech-FireFish)
- IBM Ethical Hacking with Open Source Tools Professional Certificate instructed by IBM Skills Network Team, Dee Dee Collette, Christo Oehley on Coursera platform, 2024, [URL](https://www.coursera.org/professional-certificates/ibm-ethical-hacking-with-open-source-tools).
