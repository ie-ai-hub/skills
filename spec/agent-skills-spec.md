# Agent Skills Specification

> **Source & attribution.** This document mirrors the **Agent Skills specification**
> maintained by Anthropic. The canonical, always-current version lives at
> <https://agentskills.io/specification>. Reproduced here for contributor
> convenience; if this copy and the canonical spec ever diverge, the canonical
> spec at agentskills.io takes precedence.

Skills published in this marketplace MUST conform to this specification.

## Directory structure

A skill is a directory containing, at minimum, a `SKILL.md` file:

```
skill-name/
├── SKILL.md          # Required: metadata + instructions
├── scripts/          # Optional: executable code
├── references/       # Optional: documentation
├── assets/           # Optional: templates, resources
└── ...               # Any additional files or directories
```

## `SKILL.md` format

The `SKILL.md` file must contain YAML frontmatter followed by Markdown content.

### Frontmatter

| Field           | Required | Constraints                                                                                                        |
| --------------- | -------- | ------------------------------------------------------------------------------------------------------------------ |
| `name`          | Yes      | Max 64 characters. Lowercase letters, numbers, and hyphens only. Must not start or end with a hyphen.              |
| `description`   | Yes      | Max 1024 characters. Non-empty. Describes what the skill does and when to use it.                                  |
| `license`       | No       | License name or reference to a bundled license file.                                                               |
| `compatibility` | No       | Max 500 characters. Indicates environment requirements (intended product, system packages, network access, etc.). |
| `metadata`      | No       | Arbitrary key-value mapping for additional metadata.                                                               |
| `allowed-tools` | No       | Space-separated string of pre-approved tools the skill may use. (Experimental)                                     |

**Minimal example:**

```markdown
---
name: skill-name
description: A description of what this skill does and when to use it.
---
```

**Example with optional fields:**

```markdown
---
name: pdf-processing
description: Extract PDF text, fill forms, merge files. Use when handling PDFs.
license: Apache-2.0
metadata:
  author: example-org
  version: "1.0"
---
```

#### `name` field

The required `name` field:

- Must be 1–64 characters
- May only contain unicode lowercase alphanumeric characters (`a-z`, `0-9`) and hyphens (`-`)
- Must not start or end with a hyphen (`-`)
- Must not contain consecutive hyphens (`--`)
- Must match the parent directory name

**Valid:** `pdf-processing`, `data-analysis`, `code-review`
**Invalid:** `PDF-Processing` (uppercase), `-pdf` (leading hyphen), `pdf--processing` (consecutive hyphens)

#### `description` field

The required `description` field:

- Must be 1–1024 characters
- Should describe both what the skill does and when to use it
- Should include specific keywords that help agents identify relevant tasks

**Good:** `Extracts text and tables from PDF files, fills PDF forms, and merges multiple PDFs. Use when working with PDF documents or when the user mentions PDFs, forms, or document extraction.`
**Poor:** `Helps with PDFs.`

#### `license` field

The optional `license` field specifies the license applied to the skill. Keep it short — either the name of a license or the name of a bundled license file.

```yaml
license: Proprietary. LICENSE.txt has complete terms
```

#### `compatibility` field

The optional `compatibility` field (1–500 characters) should only be included if the skill has specific environment requirements — intended product, required system packages, network access, etc. Most skills do not need it.

```yaml
compatibility: Designed for Claude Code (or similar products)
compatibility: Requires git, docker, jq, and access to the internet
compatibility: Requires Python 3.14+ and uv
```

#### `metadata` field

The optional `metadata` field is a map from string keys to string values. Clients can use it to store additional properties not defined by the spec. Use reasonably unique key names to avoid conflicts.

```yaml
metadata:
  author: example-org
  version: "1.0"
```

#### `allowed-tools` field

The optional `allowed-tools` field is a space-separated string of tools pre-approved to run. Experimental — support may vary between agent implementations.

```yaml
allowed-tools: Bash(git:*) Bash(jq:*) Read
```

### Body content

The Markdown body after the frontmatter contains the skill instructions. There are no format restrictions — write whatever helps agents perform the task effectively. Recommended sections: step-by-step instructions, examples of inputs and outputs, common edge cases.

The agent loads this entire file once it decides to activate a skill. Split longer `SKILL.md` content into referenced files.

## Optional directories

### `scripts/`

Executable code that agents can run. Scripts should be self-contained or clearly document dependencies, include helpful error messages, and handle edge cases gracefully. Supported languages depend on the agent implementation (commonly Python, Bash, JavaScript).

### `references/`

Additional documentation that agents read on demand (`REFERENCE.md`, `FORMS.md`, domain-specific files). Keep individual reference files focused and small — agents load these on demand, so smaller files mean less context use.

### `assets/`

Static resources: templates (document/configuration), images (diagrams, examples), and data files (lookup tables, schemas).

## Progressive disclosure

Agents load skills *progressively*, pulling in detail only as a task calls for it. Structure skills to take advantage of this:

1. **Metadata** (~100 tokens): `name` and `description` are loaded at startup for all skills.
2. **Instructions** (< 5000 tokens recommended): the full `SKILL.md` body is loaded when the skill is activated.
3. **Resources** (as needed): files in `scripts/`, `references/`, or `assets/` are loaded only when required.

Keep your main `SKILL.md` under 500 lines. Move detailed reference material to separate files.

## File references

When referencing other files, use relative paths from the skill root:

```markdown
See [the reference guide](references/REFERENCE.md) for details.

Run the extraction script:
scripts/extract.py
```

Keep file references one level deep from `SKILL.md`. Avoid deeply nested reference chains.

## Validation

Use the [skills-ref](https://github.com/agentskills/agentskills/tree/main/skills-ref) reference library to validate skills:

```bash
skills-ref validate ./my-skill
```

This checks that the `SKILL.md` frontmatter is valid and follows all naming conventions.
