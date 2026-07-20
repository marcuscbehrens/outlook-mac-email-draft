---
name: outlook-mac-email-draft
description: >-
  Generates ready-to-send .emltpl email files for Outlook on Mac. Use when the user asks to send, draft, compose, write, or prepare an email — or when any workflow produces output that needs to be emailed. Trigger phrases include: "send an email", "draft an email", "compose an email", "create an email to", "write an email", "prepare an email", "email this to", "forward this to".
metadata:
  version: 1.0.0
  tags: email outlook mac draft compose productivity
---

# Outlook Mac Email Draft

Generate `.emltpl` files that open directly in Outlook for Mac as compose windows with a Send button. The user just double-clicks the file and hits Send.

## When to Use

Activate this skill when the user asks to:
- Send, draft, compose, write, or prepare an email
- Forward content to someone via email
- Email a result, summary, or file to one or more people
- Create multiple emails to different recipients (e.g. a similar message personalized for each)

## How It Works

Generate one or more `.emltpl` files in the working directory. Each file is a standard RFC-2822 email message with the `.emltpl` extension, which Outlook for Mac opens in compose mode.

## File Structure

### Plain text email:

```
MIME-Version: 1.0
X-Unsent: 1
To: recipient@example.com
CC: cc-recipient@example.com
BCC: bcc-recipient@example.com
Subject: Your subject here
Content-Type: text/plain; charset="UTF-8"
Content-Transfer-Encoding: 7bit

Body text goes here.
Multiple lines are fine.
```

### HTML email:

```
MIME-Version: 1.0
X-Unsent: 1
To: recipient@example.com
CC: cc-recipient@example.com
Subject: Your subject here
Content-Type: text/html; charset="UTF-8"
Content-Transfer-Encoding: 7bit

<html>
<body>
<p>Formatted body goes here.</p>
<ul>
<li>Supports <b>bold</b>, <i>italic</i>, links, lists</li>
</ul>
</body>
</html>
```

## Rules

1. Always include `X-Unsent: 1` as one of the first headers — this tells Outlook to open in compose mode.
2. Always include `MIME-Version: 1.0`.
3. There must be exactly one blank line between the headers and the body.
4. Use `Content-Type: text/plain; charset="UTF-8"` for plain text, or `Content-Type: text/html; charset="UTF-8"` for HTML-formatted emails.
5. Use HTML format when the body contains formatting (bold, lists, tables, links). Use plain text for simple messages.
6. Save files with the `.emltpl` extension in the working directory.
7. Use descriptive filenames (e.g. `Email_to_Lara_ProjectUpdate.emltpl`).
8. Multiple recipients in To, CC, or BCC are comma-separated: `To: a@example.com, b@example.com`
9. Do NOT include a `From:` header — Outlook will use the user's default account.
10. Do NOT include a `Date:` header — Outlook will set the send date automatically.

## Multiple Emails at Once

When the user wants to send a similar message to multiple people (e.g. personalized versions of the same communication), generate multiple `.emltpl` files — one per recipient or group. Each file opens as its own compose window. The user can review and send them independently.

Example: If the user says "send this update to Anna, Ben, and Clara with their project names", create three files:
- `Email_to_Anna.emltpl`
- `Email_to_Ben.emltpl`
- `Email_to_Clara.emltpl`

## After Generating

Tell the user:
- How many `.emltpl` files were created and their filenames
- To double-click each file to open it in Outlook as a compose window
- They can review/edit and hit Send
- Multiple files can be opened simultaneously — each opens its own window
