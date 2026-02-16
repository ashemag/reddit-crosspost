# reddit-crosspost

> OpenClaw skill that crossposts your X/Twitter posts to relevant subreddits — with smart pacing, content adaptation, and subreddit-aware drafting.

Give your agent an X post URL. It finds the right subreddits, rewrites your content for each community, gets your approval, and posts via browser automation.

## How it works

```
You: "crosspost this to reddit: https://x.com/username/status/123456789"

Agent: reads tweet via browser
     → searches Reddit for relevant communities  
     → checks your subscriptions + karma
     → presents 5-7 subreddit recommendations with draft posts
     → waits for your approval

You: "post to all of them"

Agent: posts to each sub with natural pacing
     → verifies each post wasn't spam-filtered
     → reports back with links
```

## Features

| Feature | What it does |
|---------|-------------|
| **Smart pacing** | Natural timing between posts with varied intervals |
| **Content adaptation** | Every post rewritten per subreddit — different angle, title, length |
| **Casual writing style** | Concise, conversational drafts that match each community's tone |
| **Subreddit awareness** | Checks karma reqs, flair rules, title formats, posting policies before submitting |
| **Post verification** | Confirms posts appear in /new — catches silent spam filter removals |
| **Browser resilience** | Handles timeouts/crashes gracefully, prevents double-posting |
| **Time-of-day awareness** | Warns if posting during dead hours, suggests peak times |
| **Engagement follow-up** | Reminds you to reply to early comments to boost visibility |

## Why browser automation?

Reddit's API requires app registration and has strict rate limits. Browser automation lets your agent post as *you* — same session, same account, no API keys needed.

## Install

Copy `SKILL.md` into your OpenClaw skills directory:

```bash
mkdir -p ~/.openclaw/workspace/skills/reddit-crosspost
curl -o ~/.openclaw/workspace/skills/reddit-crosspost/SKILL.md \
  https://raw.githubusercontent.com/ashemag/reddit-crosspost/main/SKILL.md
```

## Prerequisites

- [OpenClaw](https://github.com/openclaw/openclaw) with browser automation enabled
- Logged into **Reddit** in the openclaw browser profile
- Logged into **X/Twitter** in the openclaw browser profile (for reading tweet content)

## Example output

After a crosspost run, you get a summary like:

```
✅ r/founder — "distribution > building right now and i don't think it's close"
   https://reddit.com/r/founder/comments/abc123

✅ r/micro_saas — "anyone else spending more time on distribution than building?"
   https://reddit.com/r/micro_saas/comments/def456

❌ r/Entrepreneur — requires 10 comment karma in sub (you have 0)

⏭️ r/startups — skipped, requires specific title prefix + strict posting rules
```

## License

MIT
