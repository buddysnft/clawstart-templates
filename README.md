# ClawStart Templates

Open-source workspace templates for [OpenClaw](https://openclaw.com) — the personal AI assistant platform for Mac.

## What This Is

Battle-tested configuration templates for OpenClaw, built from real usage across 8 specialized agents. Includes the security and protocol patterns missing from most OpenClaw setups out of the box.

Each template covers:

- **SOUL.md** — AI personality and voice
- **AGENTS.md** — Core operating rules and boot sequence
- **USER.md** — Your profile and preferences
- **IDENTITY.md** — Bot role definition and domain boundaries
- **TOOLS.md** — Integration setup notes
- **HEARTBEAT.md** — Proactive check schedule
- **MEMORY.md** — Long-term memory structure

Plus two files most setups skip:

- **SAFETY.md** — API rate limits, budget guardrails, hard stops
- **PROTOCOLS.md** — Interview-first method, memory logging, compaction recovery, batch rules

## ⚠️ Security First

**Read this before installing anything.**

OpenClaw runs locally on your Mac with your user permissions. It can execute shell commands and access files on your system.

1. **Review all files** before installing — these control AI behavior
2. **Keep OpenClaw local** — never expose port 18789 to the internet. Use `gateway.bind: "loopback"` (default)
3. **Use DM pairing** — set `dmPolicy: "pairing"` for all channels. Never use `dmPolicy: "open"`
4. **One trusted user per installation** — OpenClaw is not designed for multiple untrusted users
5. **Run a security audit after setup** — `openclaw security audit`
6. **Official security docs** — https://docs.openclaw.ai/gateway/security

## Quick Start

### Prerequisites

- OpenClaw installed (https://openclaw.com/install)
- macOS 12+ or Linux
- Basic understanding of YAML/Markdown

### Install Templates

1. Clone this repo:
```bash
git clone https://github.com/buddysnft/clawstart-templates.git
cd clawstart-templates
```

2. Copy templates to your workspace:
```bash
cp *.template ~/.openclaw/workspace/
```

3. Fill in variables (see `docs/VARIABLES.md`)

4. Rename files (remove `.template` extension):
```bash
cd ~/.openclaw/workspace
for f in *.template; do mv "$f" "${f%.template}"; done
```

5. Review and customize each file

6. Restart OpenClaw:
```bash
openclaw gateway restart
```

## Template Variables

All templates use `{{VARIABLE}}` syntax. Common variables:

- `{{USER_NAME}}` — Your full name
- `{{BOT_NAME}}` — What to call your AI
- `{{PERSONALITY}}` — Direct / Warm / Technical / Casual
- `{{USE_CASES}}` — Email, Calendar, Coding, etc.
- `{{INTEGRATIONS}}` — Telegram, Slack, GitHub, etc.

See `docs/VARIABLES.md` for the complete list.

## Documentation

- `docs/VARIABLES.md` — Complete variable reference with examples
- `docs/SAFETY.md` — Security tiers, API rules, and budget guardrails
- `docs/PROTOCOLS.md` — Core operating procedures (memory logging, compaction recovery, interview-first method)

## Want This Done For You?

DIY works fine if you want to customize everything yourself. If you want a configured workspace without the setup time, [ClawStart](https://clawstart.net) does it for you in 30 minutes.

- We run a 30-question survey to understand your workflow
- We fill in and customize all templates for your specific needs
- We handle installation and verify everything is working
- 30-day support included

Templates are free and open source. ClawStart charges for implementation. $499 one-time.

## Contributing

Contributions welcome. Especially useful:

- Better template patterns from real usage
- New personality archetypes
- Integration guides
- Security improvements

Open a PR or issue. If you have patterns worth contributing upstream to OpenClaw directly, we'll help get them there.

## License

MIT — see `LICENSE` file. Use freely, modify, distribute, build services on top of.

## Support

- **Issues/questions:** Open a GitHub issue
- **Security concerns:** See OpenClaw security docs first — https://docs.openclaw.ai/gateway/security
- **ClawStart service:** https://clawstart.net

## Links

- OpenClaw: https://openclaw.com
- OpenClaw Docs: https://docs.openclaw.ai
- OpenClaw Security: https://docs.openclaw.ai/gateway/security
- ClawStart: https://clawstart.net

---

*Community-created templates. Not affiliated with or endorsed by OpenClaw.*
