# ClawStart Templates

Open-source workspace templates for [OpenClaw](https://openclaw.com) - the personal AI assistant platform.

## What This Is

These templates provide a starting point for configuring your OpenClaw workspace. They include:

- **SOUL.md** - AI personality and voice
- **AGENTS.md** - Core operating rules
- **USER.md** - Your profile and preferences
- **IDENTITY.md** - Bot role definition
- **TOOLS.md** - Integration setup notes
- **HEARTBEAT.md** - Proactive check schedule
- **MEMORY.md** - Long-term memory structure

## ⚠️ Security First

**Before using these templates:**

1. **Review all files** - These are configuration files that control AI behavior. Read them before installing.
2. **Keep OpenClaw local** - Never expose port 18789 to the internet. Use `gateway.bind: "loopback"` (default).
3. **Use DM pairing** - Set `dmPolicy: "pairing"` for all messaging channels. Never use `dmPolicy: "open"`.
4. **Follow OpenClaw security guidance** - https://docs.openclaw.ai/gateway/security
5. **Run security audit** - After setup: `openclaw security audit`

**OpenClaw is a personal assistant trust model:**
- One trusted user per installation
- NOT designed for multiple untrusted users
- Runs with YOUR user permissions
- Can execute shell commands and access files

## Quick Start

### Prerequisites

- OpenClaw installed (https://openclaw.com/install)
- macOS 12+ or Linux
- Basic understanding of YAML/Markdown

### Using These Templates

**Option 1: Manual Customization**

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

6. Restart OpenClaw: `openclaw gateway restart`

**Option 2: Use ClawStart Service**

If you want help with customization: https://clawstart.net

- We fill in all variables based on a survey
- We provide installation support
- Templates are still open source (you're just paying for implementation)

## Template Variables

All templates use `{{VARIABLE}}` syntax. Common variables:

- `{{USER_NAME}}` - Your full name
- `{{BOT_NAME}}` - What to call your AI
- `{{PERSONALITY}}` - Direct/Warm/Technical/Casual
- `{{USE_CASES}}` - Email, Calendar, Coding, etc.
- `{{INTEGRATIONS}}` - Telegram, Slack, GitHub, etc.

See `docs/VARIABLES.md` for complete list.

## Contributing

We welcome contributions! If you have:

- Better template patterns
- New personality archetypes
- Integration guides
- Security improvements

Please open a PR or issue.

### Contribution to OpenClaw

These templates were created for the ClawStart service but are being open-sourced to help the OpenClaw community. We encourage upstream contribution of useful patterns to the OpenClaw project itself.

## License

MIT License - see `LICENSE` file

You're free to:
- Use these templates commercially or personally
- Modify them however you want
- Distribute them
- Build services on top of them

## Support

- **Issues/Questions:** Open a GitHub issue
- **Security concerns:** See OpenClaw security docs first: https://docs.openclaw.ai/gateway/security
- **ClawStart service:** https://clawstart.net (paid implementation/support)

## Credits

Created by ClawStart to solve the OpenClaw onboarding problem. Inspired by the OpenClaw community.

## Related Links

- OpenClaw: https://openclaw.com
- OpenClaw Docs: https://docs.openclaw.ai
- OpenClaw Security: https://docs.openclaw.ai/gateway/security
- ClawStart Service: https://clawstart.net

---

**Not affiliated with or endorsed by OpenClaw. These are community-created templates.**
