# Stitch Design Skills

A collection of agent skills and plugins for [Google Stitch](https://stitch.withgoogle.com), following the [Agent Skills](https://agentskills.io) open standard. Compatible with coding agents such as Antigravity, Gemini CLI, Claude Code, and Cursor.

## Quick Start

```bash
npx plugins add google-labs-code/stitch-skills
```

This installs all three plugins: **stitch-design** (6 skills), **stitch-build** (3 skills), and **stitch-utilities** (4 skills).

You can also install from a local checkout:

```bash
npx plugins add /path/to/stitch-skills
```

## Prerequisites

These skills require the **Stitch MCP** server to be configured and running in your agent's environment. Make sure you have followed the [Stitch MCP Setup Instructions](https://stitch.withgoogle.com/docs/mcp/setup/) to register the server and set up appropriate environment variables and credentials.

## Available Plugins

### Design (`stitch-design`)

Core design workflows for creating, managing, and optimizing designs within Stitch.

| Skill | Description |
|---|---|
| [code-to-design](plugins/stitch-design/skills/code-to-design/) | Convert frontend code (React, Vue, etc.) to a Stitch Design via HTML extraction + design system + upload |
| [generate-design](plugins/stitch-design/skills/generate-design/) | Generate new screens from text or images, edit existing screens, and create design variants |
| [manage-design-system](plugins/stitch-design/skills/manage-design-system/) | Manage design systems in Stitch — upload DESIGN.md and apply themes to screens |
| [extract-design-md](plugins/stitch-design/skills/extract-design-md/) | Extract a comprehensive DESIGN.md directly from frontend source code |
| [extract-static-html](plugins/stitch-design/skills/extract-static-html/) | Extract self-contained static HTML from running web apps, inlining CSS and images |
| [upload-to-stitch](plugins/stitch-design/skills/upload-to-stitch/) | Upload local assets (images, mockups, HTML) to a Stitch project |

**Prompt examples:**

> *"Upload the frontend code at `/path/to/dashboard` into a Stitch project named 'Dashboard-Migration-2026'."*

> *"Make a browse tab for a mobile app for romance and date night ideas."*

> *"Extract a high-fidelity static HTML snapshot of our local dev page running on `http://localhost:3000/profile`."*

---

### Build (`stitch-build`)

Code generation, framework integration, and asset compilation from Stitch designs.

| Skill | Description |
|---|---|
| [react-components](plugins/stitch-build/skills/react-components/) | Convert Stitch screens to React component systems with automated validation and design token consistency |
| [remotion](plugins/stitch-build/skills/remotion/) | Generate walkthrough videos from Stitch projects using Remotion with smooth transitions and zooming |
| [shadcn-ui](plugins/stitch-build/skills/shadcn-ui/) | Expert guidance for integrating and building applications with shadcn/ui components |

---

### Utilities (`stitch-utilities`)

Supporting tools for enhancing prompts, generating design specs, and enforcing design standards.

| Skill | Description |
|---|---|
| [design-md](plugins/stitch-utilities/skills/design-md/) | Analyze Stitch projects and generate comprehensive DESIGN.md files in semantic language |
| [enhance-prompt](plugins/stitch-utilities/skills/enhance-prompt/) | Transform vague UI ideas into polished, Stitch-optimized prompts with UI/UX keywords |
| [stitch-loop](plugins/stitch-utilities/skills/stitch-loop/) | Generate complete multi-page websites from a single prompt with automated validation |
| [taste-design](plugins/stitch-utilities/skills/taste-design/) | Generate DESIGN.md files enforcing premium, anti-generic UI standards |

## Repository Structure

```text
plugins/
├── stitch-design/          — Core design workflow plugin
│   ├── plugin.json
│   └── skills/
│       ├── code-to-design/
│       ├── generate-design/
│       ├── manage-design-system/
│       ├── extract-design-md/
│       ├── extract-static-html/
│       └── upload-to-stitch/
├── stitch-build/           — Code generation & build plugin
│   ├── plugin.json
│   └── skills/
│       ├── react-components/
│       ├── remotion/
│       └── shadcn-ui/
└── stitch-utilities/       — Design utilities & assistants plugin
    ├── plugin.json
    └── skills/
        ├── design-md/
        ├── enhance-prompt/
        ├── stitch-loop/
        └── taste-design/
```

Each skill follows the Agent Skills standard:

```text
skills/<skill-name>/
├── SKILL.md           — The "Mission Control" for the agent
├── scripts/           — Executable enforcers (Validation & Networking)
├── resources/         — The knowledge base (Checklists & Style Guides)
└── examples/          — The "Gold Standard" syntactically valid references
```

## Adding New Skills

All new skills need to follow the file structure above to implement the Agent Skills open standard.

### Great candidates for new skills
* **Validation**: Skills that convert Stitch HTML to other UI frameworks and validate the syntax.
* **Decoupling Data**: Skills that convert static design content into external mock data files.
* **Generate Designs**: Skills that generate new design screens in Stitch from a given set of data.

This is not an officially supported Google product. This project is not eligible for the [Google Open Source Software Vulnerability Rewards Program](https://bughunters.google.com/open-source-security).
