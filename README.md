# IE University — Claude Code Plugin Marketplace

Public [Claude Code](https://docs.claude.com/en/docs/claude-code) plugin marketplace maintained by **IE University · IT Cloud Services**.

It distributes IE's AI skills and plugins — branding/design-system skills, cloud and workplace tooling, and other agent capabilities meant to be shared.

## Add the marketplace

```
/plugin marketplace add ie-ai-hub/skills
```

## Install a plugin

```
/plugin install <plugin-name>@ie-ai-hub
```

Browse what's available with `/plugin` (interactive) or `/plugin marketplace info ie-ai-hub`.

## Available plugins

_None published yet — this marketplace is being bootstrapped._

## Publishing a plugin

Plugins are registered in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json). Each entry points at a plugin source — a folder in this repo, or another GitHub repository.

```jsonc
{
  "plugins": [
    {
      "name": "ie-brand",
      "description": "IE University brand, design system, and accessibility skills.",
      "source": "./plugins/ie-brand"
    },
    {
      "name": "ai-tools",
      "description": "IE cloud, workplace, and ops tooling.",
      "source": { "source": "github", "repo": "ie-ai-hub/ai-tools" }
    }
  ]
}
```

A plugin source must contain a `.claude-plugin/plugin.json` manifest plus its `skills/`, `commands/`, `agents/`, and/or `hooks/` directories. See the [plugin reference](https://docs.claude.com/en/docs/claude-code/plugins) for the full schema.

> Only publish content intended to be **public**. Internal-only plugins stay in the enterprise's private orgs.

---

Maintained by [IE University · IT Cloud Services](https://github.com/ie-ai-hub).
