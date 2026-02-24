---
title: "Setting Up My Development Environment & Deployment Pipeline"
date: 2026-02-24
series: "first-project"
prev: "/posts/profilePage-thirdPost/"
draft: false
tags: ["netlify", "github", "deployment", "domain", "devops"]
description: "Choosing domain, hosting, and building GitHub → Netlify automation for my first complete React project."
---


# Setting Up My Development Environment & Deployment Pipeline

*Part 3 of my "First Complete Project" series. [← Part 2: Planning with Jira](/posts/profilePage-secondPost/)*

With planning complete, my next epic was creating a professional
**development environment** and **deployment pipeline**.
This involved choosing domain registrars, hosting providers,
and setting up GitHub → Netlify automation.

## Domain Registration Decision

I compared multiple providers:

| Provider | First Year | Renewal | Notes |
|----------|------------|---------|-------|
| **Dynadot** | €6.99 | €4.99 | **Winner** - Cheapest long-term |
| Alfahosting | €27 | - | Expensive domain |
| Hetzner | €24 | - | WebHosting Bundle |

**Choice: Dynadot** for the best price/performance.

## Hosting Platform Comparison

| Platform | Cost | Pros | Cons |
|----------|------|------|------|
| **Netlify** | **Free** | Git integration, auto-deploy | Static only |
| Hetzner | €1.90/mo | Full server control | Manual setup |
| Alfahosting | €9.99+SSL | Friend's shared hosting | SSL extra cost |

**React Router Challenge:** Netlify serves static files only. React Router v7
needed server-side routing, so I switched to
**standard React Router** (client-side only, perfect for static hosting) and no
Cons because i have no Backend.

**Winner: Netlify** - Free, automatic, no compromises for my use case.

## Deployment Pipeline
Local -> GitHub -> Netlify (Automated)

- develop branch: work on
- main branch: Live branch
- Push to main → GitHub builds server files
- Netlify auto-deploys on main push

## Key Takeaways

- **Cost matters** - Free Netlify + cheap domain = €7 total first year
- **Automation saves time** - Git push → live site in 2 minutes
- **Static hosting fits** - Perfect for React + portfolio sites

<br/>

> **→ Next:** [Designing with Penpot](/posts/profilePage-fourthPost/)

*Continue reading the "First Complete Project" series.*
