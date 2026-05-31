# getacthub

> A lightweight, durable GTD system built around plain Markdown files.

**acthub** is an open-source productivity ecosystem for managing tasks, projects, and notes without vendor lock-in.

Everything is stored as Markdown files with YAML frontmatter. No database. No proprietary format. Just files you own.

---

## Ecosystem

The project is organized as a set of focused repositories, each with a single responsibility:

| Repository | Description | Status |
| --- | --- | --- |
| [`acthub-core`](https://github.com/getacthub/acthub-core) | Python library — core business logic, data model, validation | 🔜 Planned |
| [`acthub`](https://github.com/getacthub/acthub) | CLI — command-line interface built on top of `acthub-core` | 🔜 Planned |
| [`acthub-vscode`](https://github.com/getacthub/acthub-vscode) | VS Code / Windsurf extension — sidebar, quick actions, status bar | 🔜 Planned |
| [`acthub-web`](https://github.com/getacthub/acthub-web) | Web dashboard — visual interface built on top of `acthub-core` | 🔜 Planned |
| [`acthub-mcp`](https://github.com/getacthub/acthub-mcp) | MCP server — AI agent integration via Model Context Protocol | 🔜 Planned |
| [`docs`](https://github.com/getacthub/docs) | Documentation — guides, references, architecture decisions | 🔜 Planned |

---

## Architecture

```text
acthub-core   (Python library — business logic, entities, validation)
      ↑               ↑                    ↑
   acthub          acthub-web          acthub-mcp
  (CLI tool)     (web dashboard)      (MCP server)
      ↑                                    ↑
acthub-vscode ──────────────────────────────
(VS Code / Windsurf extension)
```

`acthub-core` is the foundation. `acthub` (CLI), `acthub-web`, and `acthub-mcp` all build directly on top of it.

`acthub-vscode` sits at the edge: it currently integrates with the CLI via subprocess (the standard pattern for IDE extensions wrapping CLI tools), and will progressively delegate richer interactions to `acthub-mcp` — enabling AI-powered features directly inside the editor.

Each component can be used independently: you can use the CLI alone, pair it with the VS Code extension, open the dashboard, or connect an AI agent via MCP.

---

## Status

> 🚧 This project is under active construction. APIs, data formats, and repository structure may change without notice.

We are currently focused on stabilizing `acthub-core` and `acthub` (the CLI). Other components will follow.

Feedback, issues, and contributions are welcome once the core is stable. In the meantime, feel free to watch the repositories or open a discussion.

---

## Philosophy

- **Plain files first** — your data is Markdown. It will outlive any tool.
- **CLI-native** — everything works from the terminal. GUIs are optional layers.
- **Composable** — use only what you need. No monolith.
- **Developer-friendly** — built with a CLI-first philosophy. GUIs are optional layers.
