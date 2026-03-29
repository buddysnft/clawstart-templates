# Your ClawStart Workspace - Quick Start Guide

**Welcome!** Your custom OpenClaw workspace is ready to install.

---

## What You Got

**7 Core Files** (pre-configured for you):
- `SOUL.md` - Your AI's personality
- `AGENTS.md` - Core operating rules
- `USER.md` - Your profile
- `IDENTITY.md` - Bot role definition
- `TOOLS.md` - Integration notes
- `HEARTBEAT.md` - Proactive check schedule
- `MEMORY.md` - Long-term memory structure

**Plus:**
- Folder structure (`memory/`, `projects/`, `scripts/`)
- Setup script (one command install)
- This guide

---

## Installation (2 Minutes)

### Prerequisites

1. **OpenClaw must be installed first**
   - Visit: https://openclaw.com/install
   - Follow installation guide
   - Verify: `openclaw --version`

2. **Mac Mini or MacOS machine**
   - This workspace is optimized for Mac

### Install Your Workspace

**Option A: Automatic (Recommended)**

```bash
# Download and run setup script
bash setup.sh
```

The script will:
- Backup your existing workspace (if any)
- Extract your custom files
- Set permissions
- Restart OpenClaw gateway
- Done!

**Option B: Manual**

```bash
# 1. Backup existing workspace (if you have one)
mv ~/.openclaw/workspace ~/.openclaw/workspace.backup

# 2. Extract your workspace
tar -xzf workspace-bundle.tar.gz -C ~/.openclaw/

# 3. Set permissions
chmod +x ~/.openclaw/workspace/scripts/*.sh

# 4. Restart gateway
openclaw gateway restart
```

---

## First Steps

### 1. Test Your AI

Send a message via your configured platform ({{MESSAGING_PRIMARY}}):

```
Hi! Tell me about yourself.
```

Your AI should respond in the personality you chose.

### 2. Review Your Files

Open these files and customize if needed:

- `~/.openclaw/workspace/SOUL.md` - Tweak personality
- `~/.openclaw/workspace/USER.md` - Update your info
- `~/.openclaw/workspace/HEARTBEAT.md` - Adjust proactive checks

### 3. Add Integrations

If you selected integrations (Telegram, email, calendar), follow setup guides in `TOOLS.md`.

---

## Common Tasks

### Update Your AI's Personality

```bash
# Edit SOUL.md
nano ~/.openclaw/workspace/SOUL.md

# Restart gateway to reload
openclaw gateway restart
```

### Check Daily Memory

```bash
# View today's log
cat ~/.openclaw/workspace/memory/$(date +%Y-%m-%d).md
```

### Install Skills

```bash
# Example: Install weather skill
openclaw skill install weather

# List available skills
openclaw skill list
```

---

## Troubleshooting

### AI not responding?

```bash
# Check gateway status
openclaw gateway status

# View logs
tail -f ~/.openclaw/logs/gateway.log
```

### Files not loading?

```bash
# Verify file permissions
ls -la ~/.openclaw/workspace/

# Should show your files (SOUL.md, AGENTS.md, etc.)
```

### Need to restore backup?

```bash
# If you made a mistake, restore your old workspace
mv ~/.openclaw/workspace ~/.openclaw/workspace.clawstart
mv ~/.openclaw/workspace.backup ~/.openclaw/workspace
openclaw gateway restart
```

---

## Getting Help

**Email:** support@buddysautomations.com
**Response time:** Within 24 hours (usually faster)

**Include:**
- Your order number
- What you tried
- Error messages (if any)
- Screenshots help!

**30-day support included.** We'll get you up and running.

---

## Next Steps

1. **Learn the basics** - Read `AGENTS.md` to understand how your AI works
2. **Set up integrations** - Follow guides in `TOOLS.md`
3. **Install skills** - Browse https://clawhub.ai for pre-built skills
4. **Customize** - Make it yours! Edit files, adjust personality, add workflows

---

## Pro Tips

- **Your AI logs everything** to `memory/YYYY-MM-DD.md` - Review these to see what it's learning
- **MEMORY.md grows over time** - Your AI updates it with important context
- **Heartbeats are your friend** - Let your AI proactively check things (email, calendar, etc.)
- **Back up regularly** - `tar -czf workspace-backup.tar.gz ~/.openclaw/workspace/`

---

**You're all set!** Your AI is ready to work. Start simple, build up over time.

— The ClawStart Team  
Buddys Automations
