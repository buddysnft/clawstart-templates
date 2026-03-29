# Template Variables Reference

All ClawStart templates use `{{VARIABLE}}` syntax for customization. Replace these with your values before using.

## Basic Information

| Variable | Description | Example |
|----------|-------------|---------|
| `{{USER_NAME}}` | Your full name | "John Smith" |
| `{{USER_PREFERRED_NAME}}` | What to call you | "John" |
| `{{USER_TIMEZONE}}` | Your timezone | "America/New_York" |
| `{{USER_LOCATION}}` | City, State/Country | "New York, NY" |
| `{{GENERATION_DATE}}` | When generated (auto) | "2026-03-29" |

## Bot Identity

| Variable | Description | Example |
|----------|-------------|---------|
| `{{BOT_NAME}}` | Your AI's name | "JohnBot" |
| `{{BOT_ROLE}}` | Bot's function | "Personal AI Assistant" |
| `{{BOT_MISSION}}` | Purpose statement | "I'm here to help with email and save your time." |

## Personality & Voice

| Variable | Description | Options |
|----------|-------------|---------|
| `{{PERSONALITY_DESCRIPTION}}` | How AI should behave | Direct/Warm/Technical/Casual |
| `{{VOICE_STYLE}}` | Communication style | "Short sentences. No fluff." |
| `{{COMMUNICATION_STYLE}}` | Overall approach | "Direct & efficient" |
| `{{HUMOR_LEVEL}}` | Use humor? | Yes/Occasionally/Rarely/Never |
| `{{CHALLENGE_LEVEL}}` | Push back on ideas? | "Yes, push back" / "No, just execute" |
| `{{RESPONSE_TIME}}` | Expected speed | Immediate/Hours/When asked |
| `{{PROACTIVITY_LEVEL}}` | How proactive | Very/Moderate/Minimal |

## Use Cases

| Variable | Description | Example |
|----------|-------------|---------|
| `{{USE_CASES_LIST}}` | What you want help with | "Email, Calendar, Coding" |
| `{{USE_CASES_DETAILED}}` | Detailed list | "- Email triage\n- Calendar management\n- Code assistance" |
| `{{TOP_PRIORITY}}` | #1 use case | "Email" |
| `{{TIME_SAVINGS}}` | Hours to save/week | "20 hours" |
| `{{BIGGEST_TIME_SINK}}` | Main problem | "Inbox management" |
| `{{PRIMARY_DOMAIN}}` | Focus area | "Communication & Email" |

## Goals

| Variable | Description | Example |
|----------|-------------|---------|
| `{{GOAL_30_DAYS}}` | 30-day success | "AI handles email triage daily" |
| `{{GOAL_6_MONTHS}}` | 6-month vision | "50% of communication automated" |
| `{{AUTOMATE_FIRST}}` | First tasks | "Email triage, calendar conflicts" |
| `{{CONCERNS}}` | Worries/notes | "No auto-send without approval" |
| `{{ADDITIONAL_CONTEXT}}` | Extra info | "Startup founder, speed matters" |

## Integrations

| Variable | Description | Values |
|----------|-------------|--------|
| `{{EMAIL_ACCESS}}` | Email integration | Yes Gmail/Yes Outlook/No |
| `{{CALENDAR_INTEGRATION}}` | Calendar | Yes Google/Yes Outlook/No |
| `{{GITHUB_ACCESS}}` | GitHub | Yes/No |
| `{{MESSAGING_PLATFORMS}}` | Channels | "Telegram, Slack" |
| `{{MESSAGING_PRIMARY}}` | Main channel | "Telegram" |
| `{{SOCIAL_PLATFORMS}}` | Social media | "Twitter/X, LinkedIn" |
| `{{DAILY_APPS}}` | Apps used | "Notion, Superhuman, VS Code" |
| `{{API_SERVICES}}` | External APIs | "Anthropic, OpenAI" |
| `{{EXISTING_AUTOMATIONS}}` | Current tools | "Zapier workflows" |
| `{{TECH_LEVEL}}` | Technical skill | Beginner/Intermediate/Advanced |

## Integration Flags (Boolean)

Used for conditional sections in templates:

| Variable | Description | Values |
|----------|-------------|--------|
| `{{TELEGRAM_ENABLED}}` | Telegram active | true/false |
| `{{SLACK_ENABLED}}` | Slack active | true/false |
| `{{DISCORD_ENABLED}}` | Discord active | true/false |
| `{{EMAIL_ENABLED}}` | Email active | true/false |
| `{{CALENDAR_ENABLED}}` | Calendar active | true/false |
| `{{GITHUB_ENABLED}}` | GitHub active | true/false |

## Work Hours

| Variable | Description | Example |
|----------|-------------|---------|
| `{{WORK_HOURS}}` | Schedule | "24/7" or "Morning (6-12)" |
| `{{WORK_HOURS_DESCRIPTION}}` | Detailed | "24/7 availability. No quiet hours." |
| `{{WORK_HOURS_GUIDANCE}}` | Instructions | "Never comment on time or suggest sleep" |
| `{{QUIET_HOURS}}` | Off-hours | "11 PM - 7 AM" or "None" |

## Heartbeat Configuration

| Variable | Description | Values |
|----------|-------------|--------|
| `{{PROACTIVE_EMAIL_CHECKS}}` | Auto email checks | true/false |
| `{{PROACTIVE_CALENDAR_CHECKS}}` | Auto calendar checks | true/false |
| `{{PROACTIVE_TASK_CHECKS}}` | Auto task checks | true/false |
| `{{EMAIL_CHECK_FREQUENCY}}` | How often | "Every 30 minutes" |
| `{{EMAIL_ALERT_CRITERIA}}` | What triggers alert | "Urgent messages, important contacts" |
| `{{CALENDAR_CHECK_FREQUENCY}}` | Calendar frequency | "Every 2 hours" |
| `{{DAILY_BRIEFING_ENABLED}}` | Daily summary | true/false |
| `{{DAILY_BRIEFING_TIME}}` | When | "9:00 AM" |
| `{{DAILY_BRIEFING_FORMAT}}` | Style | "Short summary (3-5 bullets)" |

## Avoid Phrases

| Variable | Description | Example |
|----------|-------------|---------|
| `{{AVOID_PHRASES}}` | Words to skip | "actually, just" or "None" |

## Operating Principles

| Variable | Description | Example |
|----------|-------------|---------|
| `{{OPERATING_PRINCIPLE_1}}` | Core rule 1 | "Proactive over reactive" |
| `{{OPERATING_PRINCIPLE_2}}` | Core rule 2 | "Document everything important" |
| `{{OPERATING_PRINCIPLE_3}}` | Core rule 3 | "Challenge bad ideas" |
| `{{OPERATING_PRINCIPLE_4}}` | Core rule 4 | "Ask when uncertain" |
| `{{DECISION_STYLE}}` | How to decide | "Question assumptions, validate approach" |

## Skills & Integrations Summary

| Variable | Description | Example |
|----------|-------------|---------|
| `{{SKILLS_LIST}}` | Installed skills | "- weather\n- calendar\n- github" |
| `{{INTEGRATIONS_SUMMARY}}` | What's connected | "**Primary:** Telegram\n**Email:** Gmail" |

## Communication Rules

| Variable | Description | Example |
|----------|-------------|---------|
| `{{COMMUNICATION_RULES}}` | How to talk | "- Be direct\n- No fluff\n- Use humor when appropriate" |

## Responsibilities

| Variable | Description | Example |
|----------|-------------|---------|
| `{{CORE_RESPONSIBILITIES}}` | What bot does | "- Email triage\n- Calendar management" |
| `{{CORE_RESPONSIBILITIES_DETAILED}}` | Detailed version | (Same with more detail) |
| `{{OUT_OF_LANE}}` | What bot doesn't do | "Tasks requiring human judgment on ethics/legal/financial" |

## Conditional Blocks

Templates use `{{#if VARIABLE}}...{{/if}}` for conditional sections:

```markdown
{{#if TELEGRAM_ENABLED}}
### Telegram Setup
...
{{/if}}
```

## Example: Filled Variables

```json
{
  "USER_NAME": "John Smith",
  "USER_PREFERRED_NAME": "John",
  "USER_TIMEZONE": "America/New_York",
  "BOT_NAME": "JohnBot",
  "PERSONALITY_DESCRIPTION": "Direct, efficient, no-nonsense",
  "USE_CASES_LIST": "Email, Calendar, Coding",
  "TOP_PRIORITY": "Email",
  "TELEGRAM_ENABLED": true,
  "EMAIL_ENABLED": true,
  "WORK_HOURS": "24/7",
  "PROACTIVITY_LEVEL": "Very"
}
```

---

**Total variables:** 73+

For automatic generation, see the ClawStart generator script or use the ClawStart service.
