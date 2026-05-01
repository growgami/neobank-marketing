# Install

Three ways to install the neobank marketing skill pack. Pick the one that matches how you work.

Skills auto-trigger on banking and fintech keywords once installed. You do not need to invoke them manually. Type something like "I run marketing at a neobank" or mention a brand like Chime, Cash App, or Revolut, and the master skill will greet you and route you to the right sub-skill.

## Method A: Project-level install

Use this when the skills should only apply inside one specific project (a single client, a single neobank brand). The skills live inside that project's `.claude/skills/` folder.

### Bash

```bash
cd /path/to/your/project
git clone https://github.com/growgami/neobank-marketing.git /tmp/neobank-marketing
mkdir -p .claude/skills
cp -r /tmp/neobank-marketing/skills/* .claude/skills/
cp -r /tmp/neobank-marketing/reference .claude/skills/neobank-marketing/
rm -rf /tmp/neobank-marketing
```

### PowerShell

```powershell
cd C:\path\to\your\project
git clone https://github.com/growgami/neobank-marketing.git $env:TEMP\neobank-marketing
New-Item -ItemType Directory -Force -Path .claude\skills | Out-Null
Copy-Item -Recurse "$env:TEMP\neobank-marketing\skills\*" .claude\skills\
Copy-Item -Recurse "$env:TEMP\neobank-marketing\reference" .claude\skills\neobank-marketing\
Remove-Item -Recurse -Force "$env:TEMP\neobank-marketing"
```

## Method B: User-level install

Use this when you want the skills available in every Claude Code project on your machine. The skills live in `~/.claude/skills/` and load globally.

### Bash

```bash
git clone https://github.com/growgami/neobank-marketing.git /tmp/neobank-marketing
mkdir -p ~/.claude/skills
cp -r /tmp/neobank-marketing/skills/* ~/.claude/skills/
cp -r /tmp/neobank-marketing/reference ~/.claude/skills/neobank-marketing/
rm -rf /tmp/neobank-marketing
```

### PowerShell

```powershell
git clone https://github.com/growgami/neobank-marketing.git $env:TEMP\neobank-marketing
New-Item -ItemType Directory -Force -Path $env:USERPROFILE\.claude\skills | Out-Null
Copy-Item -Recurse "$env:TEMP\neobank-marketing\skills\*" $env:USERPROFILE\.claude\skills\
Copy-Item -Recurse "$env:TEMP\neobank-marketing\reference" $env:USERPROFILE\.claude\skills\neobank-marketing\
Remove-Item -Recurse -Force "$env:TEMP\neobank-marketing"
```

## Method C: Git submodule for live updates

Use this when you want to pull updates from the upstream repo as the pack evolves. The skills live as a tracked submodule inside your project, and `git submodule update --remote` pulls the latest version.

### Bash

```bash
cd /path/to/your/project
git submodule add https://github.com/growgami/neobank-marketing.git .claude/skills/neobank-marketing-pack
git submodule update --init --recursive
ln -s .claude/skills/neobank-marketing-pack/skills/neobank-marketing .claude/skills/neobank-marketing
ln -s .claude/skills/neobank-marketing-pack/skills/neobank-context .claude/skills/neobank-context
```

To pull updates later:

```bash
git submodule update --remote .claude/skills/neobank-marketing-pack
```

### PowerShell

```powershell
cd C:\path\to\your\project
git submodule add https://github.com/growgami/neobank-marketing.git .claude\skills\neobank-marketing-pack
git submodule update --init --recursive
New-Item -ItemType Junction -Path .claude\skills\neobank-marketing -Target .claude\skills\neobank-marketing-pack\skills\neobank-marketing
New-Item -ItemType Junction -Path .claude\skills\neobank-context -Target .claude\skills\neobank-marketing-pack\skills\neobank-context
```

To pull updates later:

```powershell
git submodule update --remote .claude\skills\neobank-marketing-pack
```

## Verify the install

Open Claude Code in your project and ask:

> I run marketing at a neobank. Where should I start?

If the master skill triggers and greets you with the 13-skill index, you are done. If nothing happens, check that the SKILL.md files landed in the right place and that the YAML frontmatter is intact.

## First step after install

Run the `neobank-context` skill before anything else. It captures your bank profile, partner bank, regulated products, ICP, and tone target. Every other skill reads from that profile. Skipping this step gives you generic outputs that miss the point of the pack.
