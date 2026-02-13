# CT Plugin

Continuous Team plugin for Claude Code. Provides shared commands, agents, and skills for the Continuous engineering team.

## Components

### Commands
- `/ct:commit` — Create git commits following project conventions
- `/ct:create-plan` — Interactive planning process for features and tasks
- `/ct:create-spec` — Interactive feature specification creation
- `/ct:debug` — Investigate and fix bugs using debug-investigator agent
- `/ct:implement-plan` — Implement a development plan with validation phases
- `/ct:info` — Display the plugin dashboard with logo, version, mode, and available commands/agents
- `/ct:mode` — Switch between Quality and Balanced model modes
- `/ct:research-codebase` — Research the codebase with parallel agents and generate a documented report
- `/ct:review-code` — Delegate code reviews to specialized agents
- `/ct:review-plan` — Review plans for ambiguity and completeness
- `/ct:review-spec` — Review specs for clarity and identify needed clarifications

### Agents
- `@acceptance-test-pro` — Acceptance testing of implemented features against specifications
- `@code-review-expert` — Code reviews, security analysis, and code quality assessment
- `@codebase-analyzer` — Deep-dive analysis of specific codebase components
- `@codebase-locator` — Locate files, directories, and components relevant to a task
- `@codebase-pattern-finder` — Find similar implementations and existing patterns to model after
- `@database-efcore-expert` — Database design, EF Core migrations, and PostgreSQL optimization
- `@debug-investigator` — Bug investigation and unexpected behavior analysis
- `@dotnet-backend-expert` — .NET backend development, ASP.NET Core APIs, CQRS/MediatR patterns
- `@fullstack-testing-expert` — Vitest, Playwright E2E, xUnit, and integration testing strategies
- `@integration-workflow-expert` — Workflow execution, third-party API integrations, OAuth/SAML, webhooks
- `@nextjs-fullstack-expert` — Next.js 14+ App Router, server components, full-stack development
- `@react-typescript-expert` — React 18+/TypeScript, Material-UI, Recoil, TanStack Query, ReactFlow
- `@web-search-researcher` — Web search for information beyond training data

### Mode System

The plugin supports two operating modes that control which AI models are used for agent sub-tasks: `Quality` (default) or `Balanced`.

Switch modes with `/ct:mode`.

| Agent | Quality Mode | Balanced Mode |
|-------|--------------|---------------|
| `codebase-analyzer` | Opus | Opus |
| `code-review-expert` | Opus | Opus |
| `debug-investigator` | Opus | Opus |
| `codebase-pattern-finder` | Opus | Sonnet |
| `web-search-researcher` | Opus | Sonnet |
| `acceptance-test-pro` | Opus | Sonnet |
| `database-efcore-expert` | Opus | Sonnet |
| `dotnet-backend-expert` | Opus | Sonnet |
| `fullstack-testing-expert` | Opus | Sonnet |
| `integration-workflow-expert` | Opus | Sonnet |
| `nextjs-fullstack-expert` | Opus | Sonnet |
| `python-pro-backend` | Opus | Sonnet |
| `react-typescript-expert` | Opus | Sonnet |
| `codebase-locator` | Sonnet | Haiku |

## Installation

### Manual

```
/plugin marketplace add smatechnologies/continuous-tools
/plugin install ct@continuous-tools
```

### Auto-prompt for a project

Add this to your project's `.claude/settings.json` so team members are automatically prompted to install when they open the project:

```json
{
  "extraKnownMarketplaces": {
    "continuous-tools": {
      "source": {
        "source": "github",
        "repo": "smatechnologies/continuous-tools"
      }
    }
  },
  "enabledPlugins": {
    "ct@continuous-tools": true
  }
}
```

## Updates

### Manual Update
```
/plugin marketplace update continuous-tools
```

### Auto-Update
Enable automatic updates for the marketplace:
```
/plugin → Marketplaces tab → continuous-tools → Enable auto-update
```
