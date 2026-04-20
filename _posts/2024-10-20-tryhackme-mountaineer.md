---
layout: post
title: "TryHackMe: Mountaineer"
date: 2024-10-20
platform: TryHackMe
read_time: 25
tags: [Medium, Linux, WordPress, Privesc]
challenge:
  name: Mountaineer
  type: Challenge Room
  description: "The flag is what drives you, but the climb itself is what matters."
  level: Medium
  technology: Linux
  points: 60
  emoji: 🐧
  release: NEW ROOM
toc:
  - id: enumeration
    title: Enumeration
    children:
      - id: nmap-scan
        title: Nmap Scan
  - id: foothold
    title: Foothold
  - id: privilege-escalation
    title: Privilege Escalation
  - id: root-flag
    title: Root Flag
---

## Enumeration
{: #enumeration}

We start with a full port scan to identify all open services.

### Nmap Scan
{: #nmap-scan}

```bash
nmap -sC -sV -p- --min-rate 5000 10.10.x.x
```

Results show ports 22 (SSH) and 80 (HTTP) open.

## Foothold
{: #foothold}

Navigating to the web server we find a WordPress installation. Using `wpscan` to enumerate users and plugins:

```bash
wpscan --url http://10.10.x.x --enumerate u,p
```

> Found vulnerable plugin: **insert plugin name here**

## Privilege Escalation
{: #privilege-escalation}

After gaining initial access, we check for SUID binaries and sudo permissions:

```bash
sudo -l
find / -perm -u=s -type f 2>/dev/null
```

## Root Flag
{: #root-flag}

After exploiting the misconfiguration, we escalate to root and retrieve the flag:

```bash
cat /root/root.txt
```
