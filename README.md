# Outlook Mac Email Draft

Generate ready-to-send `.emltpl` email files for Outlook on Mac — just double-click and hit Send.

## What It Does

This skill enables your AI to create one or more `.emltpl` email template files in the working directory. Each file opens directly in Outlook for Mac as a compose window with a Send button — no MCP server write access required.

Use it when:
- You ask your AI to draft, compose, write, or send an email
- A workflow produces output that needs to be emailed
- You want to send personalized emails to multiple recipients at once

## Installation

```bash
npx skills add marcuscbehrens/outlook-mac-email-draft
```

Or install via the [skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add marcuscbehrens/outlook-mac-email-draft --skill outlook-mac-email-draft
```

## Usage

Start a conversation and ask your AI to send or draft an email:

- "Draft an email to john@example.com summarizing our meeting"
- "Send this report to the team"
- "Compose a follow-up email for each person on this list"

The skill triggers automatically on phrases like "send an email", "draft an email", "compose an email", "write an email", "email this to", etc.

## How It Works

The AI generates `.emltpl` files — standard RFC-2822 email messages with the `.emltpl` extension. Outlook for Mac opens these files directly in compose mode. You review the content and hit Send.

## Author

Marcus Behrens — marcus.behrens@sap.com

## License

Apache 2.0 — see [LICENSE](LICENSE)
