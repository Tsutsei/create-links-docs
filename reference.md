---
layout: page
title: Link reference
permalink: /reference/
---

A link is the address of the Create Links page plus parameters:

```
https://<your-site>.atlassian.net/jira/apps/<app>/<environment>?pid=10000&issuetype=10004&summary=Hello
```

The easiest way to get the address and the ids is the **builder**: build a link once and copy the start of it. The parameter names are the ones of Jira Server/Data Center (`CreateIssueDetails!init.jspa`).

## Parameters

| Parameter | Field | Value | Example |
|---|---|---|---|
| `pid` | Space (project) | project id | `pid=10000` |
| `issuetype` | Work type | work type id | `issuetype=10004` |
| `summary` | Summary | text | `summary=Printer%20jam` |
| `description` | Description | text; a blank line starts a new paragraph | `description=Steps%3A%0A1.%20…` |
| `environment` | Environment | text | |
| `priority` | Priority | priority id | `priority=2` |
| `assignee` | Assignee | `me` (the person opening the link) or an account id | `assignee=me` |
| `labels` | Labels | one label per parameter | `labels=web&labels=urgent` |
| `components` | Components | component id; repeat or separate with commas | `components=10100,10101` |
| `versions` | Affects versions | version id | |
| `fixVersions` | Fix versions | version id | |
| `duedate` | Due date | `YYYY-MM-DD` or a placeholder | `duedate=%7Btoday%2B7d%7D` |
| `parent` | Parent | work item id | |
| `customfield_<id>` | a custom field | see below | `customfield_10054=10021` |
| `t` | a saved link | saved link id | `t=k3j9x0a1b2c3` |
| `v1` … `v9` | values for `{1}` … `{9}` | text | `v1=Payment%20API` |

Anything else (for example `atl_token`, `os_username` from old links) is ignored and listed when the link is opened.

## Custom fields

| Field type | Value |
|---|---|
| Short text, URL | text |
| Paragraph (multi-line text) | text |
| Number | number, e.g. `42` or `3.5` |
| Date | `YYYY-MM-DD` or a placeholder like `{today+1w}` |
| Select list, radio buttons | option id |
| Multi-select, checkboxes | option id; repeat the parameter for several options |
| Labels | one label per parameter |

Other field types (user pickers, cascading selects, sprint, team, assets…) cannot be prefilled by a link; the builder lists them.

## Encoding
Values must be URL-encoded: a space is `%20` (or `+`), a line break `%0A`, `&` is `%26`, `{` `}` are `%7B` `%7D`. The builder and the converter do this for you.

## Where to find ids
- **Builder:** pick the values, the link shows their ids.
- **Project id:** open `https://<your-site>.atlassian.net/rest/api/3/project/<KEY>` while logged in; `"id"` is the project id.
- **Option ids** of a custom field: build a link with the option in the builder.

## Limits
Up to 100 parameters per link, 5 000 characters per value. A saved link can prefill up to 60 fields; a site can have up to 500 saved links.
