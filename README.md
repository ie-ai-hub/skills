# IE University — AI Skills & Plugins

Official marketplace of AI skills and plugins published by **IE University**.

This repository provides a curated, openly available catalogue of agent capabilities — corporate branding and design-system skills, cloud and workplace tooling, and other resources — for use across IE University and by the wider community. The marketplace is runtime-agnostic: the same catalogue is consumable by **Claude Code**, **Codex**, and other compatible agent runtimes.

## Installation

### Claude Code

```
/plugin marketplace add ie-ai-hub/skills
/plugin install ie-brand@ie-ai-hub
```

### Codex

```
codex plugin marketplace add https://github.com/ie-ai-hub/skills.git
codex plugin add ie-brand@ie-ai-hub
```

Use `/plugin` (Claude Code) or `codex plugin list` (Codex) to browse the full catalogue.

## Catalogue

| Plugin | Author | Description |
|---|---|---|
| **`ie-brand`** | IE University — IT UX/UI | Applies the IE University corporate design system (colours, typography, design tokens, logos) and enforces **WCAG 2.1 AA** and **European Accessibility Act (EU Directive 2019/882)** compliance on any generated or reviewed digital asset. |

## Repository structure

```
.claude-plugin/marketplace.json     Marketplace manifest
plugins/
  ie-brand/                         Branding plugin
    .claude-plugin/plugin.json
    skills/ie-brand/                Skill definition and reference assets
```

## Contributing

Contributions are coordinated by IE University IT. To propose a plugin:

1. Add a directory under `plugins/<plugin-name>/` containing a `.claude-plugin/plugin.json` manifest and one or more skills under `skills/<skill-name>/SKILL.md`.
2. Register the plugin in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) with `"source": "./plugins/<plugin-name>"`.
3. Open a pull request for review.

Only content approved for **public** distribution may be published here. Internal resources remain in IE University's private repositories. For the plugin manifest schema, see the [Claude Code plugin reference](https://docs.claude.com/en/docs/claude-code/plugins).

## Governance & contact

This marketplace is maintained by **IE University — IT Cloud Services**. Individual plugins are attributed to their authoring teams. For enquiries, contact your IE University IT representative.

---

© IE University. Maintained by [IE University · IT Cloud Services](https://github.com/ie-ai-hub).
