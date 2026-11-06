---
layout: page
title: Recipes
permalink: /recipes/
---

## "Report a bug" on a Confluence page
1. Build a link: your space, work type **Bug**, summary `Bug: `, a description with the sections you want (`Steps to reproduce`, `Expected`, `Actual`), label `from-docs`.
2. Save it as **Report a bug in the web shop**.
3. In Confluence, select a text like *Report a bug*, press **Ctrl/⌘+K** and paste the short link.

Different pages can prefill a different component or summary from the same saved link: `…?t=<id>&summary=Bug%20in%20checkout`.

## Requests by e-mail or chat
Put the link into an e-mail signature, a team channel's description or a pinned message: *"Need access to a system? [Request it here]"* – with the work type **Access request** and the space of your IT team.

## Recurring work with dates
- Weekly report: summary `Weekly report {week}/{year}`, due date `{today+4d}`.
- Onboarding: summary `Onboarding {1}`, due date `{today+14d}`; link `…?t=<id>&v1=Jane%20Doe` from the HR checklist.

## Alerts from monitoring tools
Monitoring tools can add a link to their notifications. Point it to a saved link and pass the alert's values:

```
https://<your-site>.atlassian.net/jira/apps/<app>/<env>?t=<id>&v1=<service>&v2=<alert name>
```

with a saved summary like `Incident: {2} on {1}`. The on-call person clicks the link and gets an incident with the right space, work type, priority and labels. Encode the values for URLs – for example in Grafana notification templates with `urlquery`:

```
…?t=<id>&v1={{ "{{" }} .Labels.service | urlquery {{ "}}" }}&v2={{ "{{" }} .Labels.alertname | urlquery {{ "}}" }}
```

## A QR code on equipment
Make a saved link per printer, meeting room or machine (summary `Problem with {1}`, `v1=Printer 3rd floor`), turn it into a QR code with any QR code generator and stick it on the device. People scan it, log in to Jira and report the problem with the device already named.

## Browser bookmark
Save the link as a bookmark (for example *New bug – web shop*) for work items you create often. Bookmarks with placeholders always have the current dates.

## Help desk without a portal
For team-managed spaces without Jira Service Management, a saved link with the work type **Request** and a description template is a lightweight intake form – people still need to be users of the Jira site.
