---
layout: post
title: "HackTheBox: Underpass"
date: 2024-10-12
platform: HackTheBox
read_time: 18
tags: [Easy, Linux, SNMP, Mosh]
challenge:
  name: Underpass
  type: Machine
  description: "Enumerate services carefully — what's hidden under the surface."
  level: Easy
  technology: Linux
  points: 20
  emoji: 📦
toc:
  - id: enumeration
    title: Enumeration
  - id: foothold
    title: Foothold
  - id: root
    title: Root
---

## Enumeration
{: #enumeration}

```bash
nmap -sC -sV 10.10.11.x
```

SNMP is running — let's enumerate it:

```bash
snmpwalk -c public -v1 10.10.11.x
```

## Foothold
{: #foothold}

SNMP reveals credentials. Use them to SSH in.

## Root
{: #root}

Check for Mosh running as root — exploit the misconfiguration to escalate.

```bash
cat /root/root.txt
```
