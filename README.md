# reddit-crosspost

An OpenClaw skill that crosspost your X/Twitter posts to Reddit — finding relevant subreddits, adapting content for each community, and posting via browser automation.

## What it does

Give it an X post URL and it will:

1. Read the tweet content via browser
2. Find relevant subreddits (searching Reddit + checking your subscriptions)
3. Present recommendations with draft posts tailored to each sub
4. Wait for your approval before posting anything
5. Post via browser automation with human-speed pacing
6. Verify posts landed (checks for spam filter removals)
7. Report back with links to all successful posts

## Why browser automation?

Reddit's API requires app registration and has strict rate limits. Browser automation lets your agent post as *you* — same session, same account, no API keys. The skill includes detailed pacing rules so your account doesn't get flagged.

## Key features

- **Human-speed pacing** — Slow typing, random delays between posts, natural browsing patterns between submissions
- **Content variation** — Every post is meaningfully rewritten per subreddit (different angle, title structure, length). No cookie-cutter spam.
- **Subreddit rules awareness** — Checks for karma requirements, flair, title formats, and anti-promo rules before posting
- **Sound human, not like AI** — Detailed writing guide to avoid "AI slop" detection. Lowercase titles, casual tone, imperfect grammar on purpose.
- **Post verification** — Confirms each post actually appears in /new and wasn't silently spam-filtered
- **Browser resilience** — Handles timeouts and crashes gracefully, avoids double-posting
- **Time-of-day awareness** — Suggests better posting times if you're about to post at 3am
- **Engagement reminders** — Prompts you to reply to early comments so posts don't look like drive-by spam

## Install

Copy `SKILL.md` to your OpenClaw workspace skills directory:

```
~/.openclaw/workspace/skills/reddit-crosspost/SKILL.md
```

Or install the packaged skill:

```
openclaw skill install reddit-crosspost.skill
```

## Prerequisites

- OpenClaw with browser automation enabled (`openclaw` browser profile)
- Logged into Reddit in the browser
- Logged into X/Twitter in the browser (for reading tweet content)

## Usage

Just share an X post URL with your agent:

> "crosspost this to reddit: https://x.com/username/status/123456789"

The agent will handle the rest — finding subs, drafting posts, and waiting for your go-ahead before posting.

## License

MIT
