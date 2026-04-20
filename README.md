# YourHandle — CTF Blog

A fully working Jekyll blog for CTF writeups, styled like Str4ngerX's portfolio.

---

## 🚀 Deploy to GitHub Pages (Step by Step)

### 1. Create the repo
Go to github.com → New repository  
Name it exactly: `yourusername.github.io`  
Set it to **Public**

### 2. Upload all these files
Either drag-and-drop in the GitHub UI, or use git:
```bash
git init
git add .
git commit -m "initial blog"
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

### 3. Enable GitHub Pages
Go to your repo → **Settings** → **Pages**  
Source: **GitHub Actions** → select **Jekyll**  
GitHub will auto-detect and build it.

### 4. Your site is live at:
`https://yourusername.github.io`

---

## ✍️ Writing a New Writeup

Create a file in `_posts/` named: `YYYY-MM-DD-title.md`

**Example:** `_posts/2024-11-01-hackthebox-cicada.md`

```markdown
---
layout: post
title: "HackTheBox: Cicada"
date: 2024-11-01
platform: HackTheBox        # HackTheBox / TryHackMe / CTF
read_time: 20
tags: [Easy, Windows, Active Directory]
challenge:
  name: Cicada
  type: Machine
  description: "Your short description here."
  level: Easy               # Easy / Medium / Hard
  technology: Windows       # Linux / Windows / etc
  points: 20
  emoji: 📦                 # emoji for the mascot circle
toc:
  - id: enumeration
    title: Enumeration
    children:
      - id: nmap-scan
        title: Nmap Scan
  - id: foothold
    title: Foothold
  - id: root
    title: Root
---

## Enumeration
{: #enumeration}

Your writeup content here...

### Nmap Scan
{: #nmap-scan}

```bash
nmap -sC -sV 10.10.11.x
```
```

That's it — push to GitHub and it publishes automatically.

---

## ⚙️ Customize _config.yml

```yaml
title: YourHandle
description: "Walkthroughs, writeups and guides!"
author:
  name: YourHandle
  github: https://github.com/yourusername
  linkedin: https://linkedin.com/in/yourusername
  avatar: /assets/img/avatar.jpg   # add your photo here
```

## 🏃 Run locally (optional)

```bash
gem install bundler
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```
