---
layout: page
title: Migrating from Data Center
permalink: /migration/
---

Jira Server and Data Center open a prefilled create screen with links like

```
https://jira.example.com/secure/CreateIssueDetails!init.jspa?pid=10000&issuetype=1&summary=Hello&priority=3
```

In Jira Cloud these addresses fill in at most the project and the work type, and Atlassian is retiring the old create page. Create Links uses the **same parameter names**, so a link only needs a new address.

## 1. Find your old links
- Confluence: search for `CreateIssueDetails` and `CreateIssue.jspa`.
- Intranet, wikis, e-mail templates, monitoring tools, bookmarks shared in your teams.

## 2. Convert them
In **Apps → Create Links → Convert a Data Center link**, paste an old link. You get the Cloud link and a list of parameters that were left out (`atl_token`, `os_username` and other parameters that are not fields).

## 3. Check the ids
A migration can change ids: of spaces (projects), work types, priorities, components, versions, custom fields and their options. After the migration:

1. Open the converted link once (or **Try it** in the builder).
2. If a field stays empty or the wrong space opens, build the link in the builder, which uses the ids of your Cloud site, and replace the old one.
3. For links used in many places, **save** them: later changes happen in one place.

## What is different in Cloud
- Fields are filled in the **create dialog**, not on a separate page.
- `description` and `environment` are plain text (a blank line starts a new paragraph).
- Placeholders (`{today+7d}`, `{1}` …) and saved links are new in Create Links.
- User pickers other than the assignee cannot be prefilled.
