# Dangerous Professional Plugin

A plugin for **Claude Code** and **Codex CLI** implementing Patrick McKenzie's (patio11) [Dangerous Professional](https://www.kalzumeus.com/2017/09/09/identity-theft-credit-reports/) framework for strategic professional communication.

> "Memetically, being a Dangerous Professional means communicating in what might be a slightly adversarial context in a way which suggests that a bureaucracy take one's concerns seriously and escalate them to someone empowered to resolve them swiftly." — [@patio11](https://x.com/patio11/status/1162561822248992768)

## What It Does

This plugin provides a skill that helps you write firm, specific, rights-aware correspondence when dealing with institutions: banks, insurance companies, contractors, landlords, employers, government agencies, medical providers, collections agencies, or any bureaucracy.

It doesn't generate templates. It runs an interview-driven workflow that:

1. Understands your situation
2. Reads your documents (contracts, invoices, denial letters)
3. Identifies your leverage — what the institution has already conceded in their own records
4. Calibrates tone to the appropriate level
5. Drafts a communication grounded in their documents, not your feelings
6. Reviews against known failure modes before presenting

## Installation

### Claude Code

```bash
claude plugin add tobthecreator/dangerous-professional-plugin
```

### Codex CLI

```bash
codex plugin install tobthecreator/dangerous-professional-plugin
```

### Any Agent (Cursor, Windsurf, Cline, Copilot, 40+ others)

Via the [skills ecosystem](https://github.com/vercel-labs/skills):

```bash
npx skills add tobthecreator/dangerous-professional-plugin
```

Target a specific agent:

```bash
npx skills add tobthecreator/dangerous-professional-plugin -a cursor
npx skills add tobthecreator/dangerous-professional-plugin -a windsurf
npx skills add tobthecreator/dangerous-professional-plugin -a cline
```

## Usage

The skill triggers automatically when you describe a dispute with an institution. You can also invoke it explicitly:

**Claude Code:**
```
/dangerous-professional
```

**Codex CLI:**
```
$dangerous-professional
```

For best results, have your documents ready — contracts, invoices, letters, emails, denial notices. The strongest Dangerous Professional move is citing the institution's own records back to them.

## Core Principles

Drawn from McKenzie's published work:

- **Don't negotiate against yourself** — never pre-compromise
- **Specificity is power** — dates, amounts, names, reference numbers
- **Emotionlessness over anger** — cold competence is more threatening than rage
- **Paper trails are the weapon** — meticulous documentation IS the implicit threat
- **"Require" not "demand"** — word-level register choices signal which world you operate in
- **Strategic ambiguity** — "I will avail myself of remedies available under law"
- **Their documents are your evidence** — reference their records, not your narrative
- **Brevity signals professional** — 100-200 words, not 500

## Attribution

This plugin packages the strategic communication framework developed by [Patrick McKenzie](https://www.kalzumeus.com/) ([@patio11](https://x.com/patio11)) across his extensive writing, particularly:

- [Identity Theft, Credit Reports, and You](https://www.kalzumeus.com/2017/09/09/identity-theft-credit-reports/) (2017)
- [Salary Negotiation: Make More Money, Be More Valued](https://www.kalzumeus.com/2012/01/23/salary-negotiation/) (2012)
- [Talking About Money](https://www.kalzumeus.com/2015/05/01/talking-about-money/) (2015)
- His ongoing Twitter threads on the Dangerous Professional concept

This is a community project with no affiliation to Patrick McKenzie or Stripe.

## Project Structure

```
.claude-plugin/
  plugin.json                       # Claude Code manifest
  marketplace.json                  # Claude Code marketplace entry
.codex-plugin/
  plugin.json                       # Codex CLI manifest
skills/dangerous-professional/      # Universal skill (Codex, npx skills, 40+ agents)
  SKILL.md
  agents/openai.yaml                # Codex UI metadata
  references/                       # Shared reference files (source of truth)
claude-skills/dangerous-professional/ # Claude Code skill
  SKILL.md
  references -> symlink to shared
```

The five reference files (principles, tone guide, escalation paths, examples, gotchas) live in `skills/` and are shared via symlink. The `skills/` SKILL.md uses relative paths (universal); the `claude-skills/` version uses `${CLAUDE_SKILL_DIR}` variable substitution required by Claude Code.

## Contributing

Issues and PRs welcome. The highest-value contributions are:

- New entries in `references/gotchas.md` from real failure modes you've encountered
- Additional annotated examples in `references/examples.md`
- Escalation path updates in `references/escalation.md` (regulatory contacts change)

## License

MIT
