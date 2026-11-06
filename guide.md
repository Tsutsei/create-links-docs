---
layout: page
title: User guide
permalink: /guide/
---

## Where to find it
In Jira: **Apps → Create Links** (in the sidebar under "Apps"). Every user of the site can open it, build links and open links. Saving shared links is for space admins and Jira admins.

## Build a link
1. **Space** – the space (project) the work item goes to. You see the spaces where you can create work items.
2. **Work type** – Bug, Task, Story, … of that space.
3. **Fields** – the fields of that work type's create screen are listed. Fill in what the link should prefill; leave the rest empty. People can still change every value in the dialog before they create the work item.
   - **Assign to the person who opens the link** sets the assignee to whoever clicks the link.
   - **Labels** are separated by spaces.
   - Fields a link cannot fill (for example attachments, linked work items, sprint, team) are listed under the fields.
4. **Your link** shows the link. Copy it, or click **Try it** to open the create dialog with it.

The link contains the values themselves, so you can share it right away – nothing has to be saved.

## Save a shared link
Under **Save as a shared link** give the link a name and click **Save link**. You get a short link like `…?t=k3j9x0a1b2c3`.

- Change a saved link later in **Saved links → Edit**; every place that uses the short link follows.
- **Delete** removes it; the short link then explains that it no longer exists.
- Space admins can save, change and delete links of their spaces, Jira admins of all spaces. Everyone sees the saved links of the spaces they can browse.

## Placeholders
Placeholders are replaced when someone opens the link, in their time zone:

| Placeholder | Becomes | Example |
|---|---|---|
| `{today}` | today's date | `2026-11-06` |
| `{today+7d}` `{today-3d}` | days from today | due date `{today+7d}` |
| `{today+2w}` | weeks from today | |
| `{today+1m}` | months from today (end of month kept) | |
| `{week}` | ISO week number | `Weekly report {week}` → `Weekly report 45` |
| `{month}` | year and month | `2026-11` |
| `{year}` | year | `2026` |
| `{1}` … `{9}` | the value of `v1` … `v9` in the link | `Outage of {1}` with `&v1=Payment%20API` |

Use them in any text field, in date fields (`{today+14d}`) and in saved links.

## One saved link, many uses
A saved link takes extra values from its address:

- `…?t=k3j9x0a1b2c3&v1=Payment%20API` fills `{1}` in the saved summary.
- `…?t=k3j9x0a1b2c3&summary=Printer%20on%203rd%20floor` replaces the saved summary; all other saved values stay.

So a single "Report an incident" link can serve every Confluence page of your services, each page adding its service name.

## Open a link
The create dialog opens at once. After creating, the new work item's key is shown with a link to it. **Create another** opens the dialog again with the same values; if you close the dialog without creating, **Open the dialog again** brings it back.

If a link contains a value that cannot be used (for example an invalid priority id) or a parameter that is not a field, the page tells you which one was left out – the rest is still filled in.

## Licence
Create Links is free for sites with up to 10 users. On larger sites it needs an active subscription; without it links do not open and the page says so.
