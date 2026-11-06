---
layout: page
title: FAQ
permalink: /faq/
---

**Who can use a link?**
Every user of your Jira site who can create work items in the link's space. The create dialog checks the user's permissions as usual; people without access see Jira's own message.

**Can people outside our site use the links?**
No. They must be logged in to your Jira site. Create Links is not a public form.

**Does the app create the work item?**
No. Jira's own create dialog does, as the user. People can change every prefilled value before they click Create; required fields and validators apply as usual.

**Who can save, change and delete shared links?**
Space admins for their spaces and Jira admins for all spaces. Everyone can build and share links without saving them.

**Can a link hide or lock a field?**
No. A link only fills in values; the user sees and can change all fields of the create screen.

**Which fields can a link fill?**
See the [link reference]({{ '/reference/' | relative_url }}). User pickers (except the assignee), cascading selects, sprint, team and assets fields cannot be prefilled.

**What does the app store?**
Only saved links: name, space, work type and default values. No personal data, nothing about who opened a link. See the [privacy policy]({{ '/privacy/' | relative_url }}).

**Does it work with Jira Service Management, Jira Software and Jira Work Management spaces?**
Yes, the link opens Jira's create dialog for the chosen space and work type. For JSM customers who use the portal, a portal request link is the better fit.

**Is a saved link's content secret?**
No. Anyone on the site who has the short link sees its values in the create dialog, just as with a full link. Do not put passwords or secrets into links.

**What happens to links after uninstalling?**
They stop working; saved links are deleted with the app's data.
