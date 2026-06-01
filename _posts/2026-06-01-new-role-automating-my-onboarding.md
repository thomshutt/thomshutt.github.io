---
layout: post
title: "Using Cursor Automations to onboard faster"
date: 2026-06-01
tags: ["automation", "fastly", "onboarding", "cursor", "brevo"]
description: "How I used Cursor and Brevo to get up to speed faster with a large org's codebase"
og_image: /assets/img/2026-06-01-new-role-automating-my-onboarding/header.png
header_image: /assets/img/2026-06-01-new-role-automating-my-onboarding/header.png
---

# Using Cursor Automations to onboard faster

I was recently lucky enough to start a new role at [Fastly](https://fastly.com). It's a relatively large company at over 1,000 employees and even though I'm a former customer, has lots of product surface area that I'm not familiar with. 

When [Cursor](https://cursor.com/) recently released their [Automations](https://cursor.com/docs/cloud-agent/automations) feature, I realised I could test it out by beginning to "watch"  the [open-source Fastly repos](https://github.com/fastly/) ahead of joining and start to get a bit of a sense of where development was happening and what kinds of features were shipping.

## Configuring the automation

Config was mostly straightforward and consisted of:

1. Choosing a trigger (I went for periodic, but there were a small set of integrations for common SAAS platforms as well as webhook triggers)
2. Giving a prompt to the agent. I did a bit of tweaking over the first few runs to make it give the level of context I was looking for.
3. Giving it the ability to email me. This was the most fiddly bit, since there isn't currently a built-in email integration. Luckily I found the excellent [Brevo](https://developers.brevo.com/docs/mcp-protocol) which not only has a generous free tier but also has an MCP server, which I configured in Cursor and can now refer to whenever I want an automation to email me.

![](/assets/img/2026-06-01-new-role-automating-my-onboarding/config.png)

## The results

After tweaking the amount of context, the whole workflow seemed to work perfectly and is now delivering daily summaries that are helping me to get to grips with at least one piece of the puzzle of joining a new company.

![](/assets/img/2026-06-01-new-role-automating-my-onboarding/email.png)

## Automations

In general they seem to be working really well, with the following nits:
- No granularity or flexibility in terms of the timing - you're limited to the set (hourly, daily etc.) of options they provide
- Limited set of built-in integrations for outputs. I was lucky that Brevo had a generous free tier and an MCP server, otherwise the options were Github, Teams and Slack.
- The usual LLM reliability concerns. Doing this kind of thing without code scaffolding around the core parts (fetching all PRs since the last run) means that there will probably be times when it misses PRs or subtly does the wrong thing. For this kind of use case though, that level of errors is fine.
