# reddit-crosspost

> OpenClaw skill that crossposts your X/Twitter posts to relevant subreddits — with human-speed pacing, content variation, and anti-detection built in.

Give your agent an X post URL. It finds the right subreddits, rewrites your content for each community, gets your approval, and posts via browser automation — all while looking like a real person, not a bot.

## How it works

```
You: "crosspost this to reddit: https://x.com/username/status/123456789"

Agent: reads tweet via browser
     → searches Reddit for relevant communities  
     → checks your subscriptions + karma
     → presents 5-7 subreddit recommendations with draft posts
     → waits for your approval

You: "post to all of them"

Agent: posts to each sub with 3-5 min random gaps
     → types slowly, browses between posts
     → verifies each post wasn't spam-filtered
     → reports back with links
```

## Features

| Feature | What it does |
|---------|-------------|
| **Human-speed pacing** | Slow typing, random delays (3-5 min), natural browsing between posts |
| **Content variation** | Every post rewritten per subreddit — different angle, title, length. 40%+ word difference enforced |
| **Anti-AI writing** | Lowercase titles, casual tone, deliberate imperfections. Passes Reddit's AI detection |
| **Subreddit awareness** | Checks karma reqs, flair rules, title formats, anti-promo policies before posting |
| **Post verification** | Confirms posts appear in /new — catches silent spam filter removals |
| **Browser resilience** | Handles timeouts/crashes gracefully, prevents double-posting |
| **Time-of-day awareness** | Warns if posting during dead hours, suggests peak times |
| **Engagement follow-up** | Reminds you to reply to early comments so posts don't look like drive-by spam |

## Why browser automation?

Reddit's API requires app registration and has strict rate limits. Browser automation lets your agent post as *you* — same session, same account, no API keys needed. The skill includes detailed pacing rules so your account doesn't get flagged.

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

⏭️ r/startups — skipped, requires "i will not promote" prefix + strict AI rules
```

## Writing style

The skill includes a detailed writing guide to avoid "AI slop" detection on Reddit:

**Bad** (sounds like AI):
> "Building products has changed more in the last month than in the last decade. Everyone is more focused on distribution than ever. Here's a great conversation about the 2026 tech media strategy."

**Good** (sounds human):
> "anyone else feel like the distribution conversation has completely taken over? like six months ago everyone was heads down shipping, now it's all about how you get seen. caught this pod ep that actually had decent takes on what's working rn https://x.com/..."

## License

MIT
