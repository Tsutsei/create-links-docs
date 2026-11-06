---
layout: page
title: Overview
permalink: /
---

**Create Links – Prefilled Create Issue Links for Jira** gives Jira Cloud links that open the Jira create dialog with the fields already filled in: space, work type, summary, description, priority, labels, components, versions, due date, assignee and custom fields.

Put such a link anywhere people start work: a Confluence page, an e-mail, a browser bookmark, a chat message, a monitoring alert or a QR code on a printer. One click, and the native Jira create dialog opens – filled in, with the user's own permissions and your field rules.

```
https://your-site.atlassian.net/jira/apps/…/…?pid=10000&issuetype=10004&summary=Printer%20jam&labels=facilities
```

## Why
Jira Server and Data Center could do this with `CreateIssueDetails!init.jspa?pid=…&summary=…`. Jira Cloud opens its create dialog empty. Create Links brings the feature back – with the same parameter names, so links from Data Center only need a new address.

## What you get
- **Prefilled links** for every field of the create screen that a link can fill: text, paragraph, number, date, select, multi-select, labels, priority, components, versions, assignee.
- **A link builder** – choose a space and a work type, fill in the fields, copy the link. No URL syntax to learn.
- **Saved links** – short links (`?t=…`) that space admins can change later; every page and e-mail that uses the link follows.
- **A create menu in every space** – the saved links of a space appear on its Create Links page, one click per template.
- **Placeholders** – `{today+7d}` for a due date a week ahead, `{week}` in a weekly report, `{1}`…`{9}` for values that come with the link.
- **A converter for Data Center links**, see [Migrating from Data Center]({{ '/migration/' | relative_url }}).

## Safe by design
- The work item is created by **Jira's own create dialog, as the user**. Jira checks the user's permissions, required fields and validators as usual; the app never writes to Jira.
- **No personal data** is stored. A saved link holds its name, space, work type and default values – nothing else.
- **Runs on Atlassian**: no data leaves Atlassian, no external servers.

## Get started in a minute
1. Open **Apps → Create Links** in Jira.
2. Choose a space and a work type, fill in a summary and whatever else should be prefilled.
3. Copy the link under **Your link**, or click **Try it**.

Read the [user guide]({{ '/guide/' | relative_url }}), browse the [recipes]({{ '/recipes/' | relative_url }}) or look up a parameter in the [link reference]({{ '/reference/' | relative_url }}).
