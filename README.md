# IE University — AI Skills & Plugins

Public plugin marketplace maintained by **IE University · IT Cloud Services**.

It distributes IE's AI skills and plugins — branding/design-system skills, cloud and workplace tooling, and other agent capabilities meant to be shared. The same marketplace works in both **Claude Code** and **Codex** (the `.claude-plugin` format is shared across runtimes).

## Claude Code

```
/plugin marketplace add ie-ai-hub/skills
/plugin install ie-brand@ie-ai-hub
```

## Codex

```
codex plugin marketplace add https://github.com/ie-ai-hub/skills.git
codex plugin add ie-brand@ie-ai-hub
```

(`codex plugin list` shows everything the marketplace offers; `codex plugin marketplace list` shows configured marketplaces.)

## Available plugins

| Plugin | Description |
|---|---|
| **`ie-brand`** | IE University branding plugin. Applies the corporate design system (colors, typography, design tokens, logos) and enforces **WCAG 2.1 AA** / **European Accessibility Act** compliance on any generated or reviewed digital asset. First skill: `ie-brand`. |

## Repository layout

```
.claude-plugin/marketplace.json     # marketplace manifest (name: ie-ai-hub)
plugins/
  ie-brand/                         # the branding plugin
    .claude-plugin/plugin.json
    skills/
      ie-brand/
        SKILL.md
        references/                 # design tokens (CSS/JSON), school logos
```

## Publishing a plugin

1. Add a folder under `plugins/<plugin-name>/` with a `.claude-plugin/plugin.json` manifest and its `skills/<skill-name>/SKILL.md` (plus optional `commands/`, `agents/`, `hooks/`).
2. Register it in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) with `"source": "./plugins/<plugin-name>"`.
3. Open a PR.

See the [plugin reference](https://docs.claude.com/en/docs/claude-code/plugins) for the full schema.

> Only publish content intended to be **public**. Internal-only plugins stay in the enterprise's private orgs.

---

Maintained by [IE University · IT Cloud Services](https://github.com/ie-ai-hub).
