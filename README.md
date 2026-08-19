# Quasar Framework Agent Skills

Reusable AI agent skills for building, maintaining, and extending applications with [Quasar Framework](https://quasar.dev/).

## Install

Install every skill:

```bash
npx skills add quasarframework/agent-skills
```

List the available skills:

```bash
npx skills add quasarframework/agent-skills --list
```

Install one skill:

```bash
npx skills add quasarframework/agent-skills --skill quasar-electron-development
```

## Agent support

The skills use the portable `SKILL.md` format and can be installed for Claude Code, Codex, Cursor, Gemini CLI, GitHub Copilot, Windsurf, and other compatible agents.

Install for Claude Code:

```bash
npx skills add quasarframework/agent-skills --agent claude-code
```

Or add the repository as a native Claude Code plugin marketplace and install the complete collection:

```text
/plugin marketplace add quasarframework/agent-skills
/plugin install quasar-framework-skills@quasar-framework-agent-skills
```

Install for Codex:

```bash
npx skills add quasarframework/agent-skills --agent codex
```

Install for every agent detected on the system:

```bash
npx skills add quasarframework/agent-skills --all
```

Each skill's `SKILL.md` is the shared source of instructions. Files under `agents/` contain optional agent-specific integration metadata and do not restrict which agents can use a skill. `agents/openai.yaml` improves the Codex interface; Claude Code safely ignores it and uses `SKILL.md` directly. The `.claude-plugin/` manifests expose the complete collection through Claude Code's native plugin marketplace.

Claude-specific behavior, when a skill genuinely requires it, belongs in the supported `SKILL.md` frontmatter rather than an `agents/claude.yaml` file. These skills currently require no Claude-only permissions or invocation behavior.

## Skills

| Skill | Scope |
| --- | --- |
| `quasar-development` | Shared Quasar application architecture, configuration, UI, testing, and maintenance |
| `quasar-app-extension-development` | Quasar App Extension creation, lifecycle hooks, prompts, templates, and publishing |
| `quasar-spa-development` | Single-page application development and deployment |
| `quasar-ssr-development` | Server-side rendering, hydration, middleware, webservers, and deployment |
| `quasar-ssg-development` | Static generation, route discovery, SEO, partial CSR, and deployment |
| `quasar-pwa-development` | Progressive Web Apps, manifests, service workers, caching, and installability |
| `quasar-capacitor-development` | iOS and Android applications built with Capacitor |
| `quasar-cordova-development` | iOS and Android applications built with Cordova |
| `quasar-electron-development` | Secure cross-platform desktop applications with Electron |
| `quasar-bex-development` | Browser extensions, content scripts, background scripts, and BEX bridge communication |

Mode-specific skills complement `quasar-development`; invoke both when a task spans general application code and platform concerns.

## Contributing

Keep instructions grounded in current Quasar behavior and link to official documentation for details that can change between releases. Each skill must contain a valid `SKILL.md` and matching `agents/openai.yaml` metadata.
