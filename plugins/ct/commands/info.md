# Plugin Info

You are tasked with displaying the ct plugin's info dashboard. Output the logo, version, current mode, and available commands/agents.

## Process

1. **Read current mode** from `plugins/ct/config/mode.md`. Default to `quality` if missing or unreadable.

2. **Output the following exactly** (replace `[MODE]` with the current mode capitalized, e.g., `Quality` or `Balanced`):

```
────────────────────────────────────────────────────────────────────────────────

       #############               #############
    ###################         ###################
  ##### ########## ######      #### ########### ####
 #### ####################  ##### ############### ####
#### ####        ##### ########  ####         #### ###
### ####           ####  ##### #####           #### ###
### ###              # ##### #####              ### ###
### ###              ##### # #####              ### ###
### ####           #####  #### #####           #### ###
#### ####        ##### ### ##### #####       ##### ###
 #### ############## #####   ################### ####
  ###### ######### #####       ##### ######### #####
    ##################           #################
       ############                 ###########

  v1.0.0                                          Continuous Tools for Claude Code
  
  ────────────────────────────────────────────────────────────────────────────────

  Mode        [MODE]
  Agents      14 available
  Commands    10 loaded

  ────────────────────────────────────────────────────────────────────────────────

  Commands (in suggested order of execution)
    /ct:create-spec       Create a feature specification interactively
    /ct:review-spec       Review a spec for clarity and completeness
    /ct:research-codebase Research a particular aspect of the codebase in depth
    /ct:create-plan       Build an implementation plan (provide spec and/or research doc)
    /ct:review-plan       Review a plan for ambiguity and feasibility
    /ct:implement-plan    Execute a plan with incremental validation
    /ct:commit            Create a git commit following project conventions
    /ct:review-code       Delegate a code review to a specialized agent
    /ct:mode              Switch between Quality and Balanced modes
    /ct:info              Show this dashboard

  ────────────────────────────────────────────────────────────────────────────────

  Agents
    Tier 1  codebase-analyzer  code-review-expert  debug-investigator
    Tier 2  codebase-pattern-finder  web-search-researcher  dotnet-backend-expert
            react-typescript-expert  nextjs-fullstack-expert  python-pro-backend
            database-efcore-expert  integration-workflow-expert  acceptance-test-pro
            fullstack-testing-expert
    Tier 3  codebase-locator
```

## Important
- Output the dashboard as-is. Do not add any commentary before or after it.
- The only dynamic value is `[MODE]` — replace it with the current mode from the config file.
- Use a monospace-friendly layout. The ASCII art and table lines should render cleanly in the terminal.
