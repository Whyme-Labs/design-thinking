# Design Thinking Skill

A Claude Code skill that guides users through the Stanford d.school design thinking framework: **Empathize, Define, Ideate, Prototype, Test**.

## Installation

```bash
claude mcp add design-thinking -- npx @anthropic-ai/claude-code-mcp@latest skill install Whyme-Labs/design-thinking
```

Or add it manually to your Claude Code settings:

```json
{
  "permissions": {
    "allow": [
      "skill:design-thinking"
    ]
  }
}
```

## Usage

Once installed, invoke the skill in Claude Code:

```
/design-thinking
```

Or simply describe your problem and mention "design thinking":

```
I want to use design thinking to explore how we can improve our onboarding flow
```

The skill will guide you through all 6 phases interactively, one step at a time.

## Requirements

- Claude Code with Agent tool support
- WebSearch access (for the critic's existing solutions research)

## Architecture

This is a pure markdown orchestrator skill (no code, no Worker). The orchestrator protocol lives in `SKILL.md`, which dispatches subagent prompts from `prompts/` and references techniques from `reference/`.

```
design-thinking/
├── SKILL.md                  # Orchestrator protocol (main entry point)
├── prompts/                  # Subagent prompt files
│   ├── critic.md             # Adversarial reviewer (runs every phase)
│   ├── persona-interviewer.md # Simulates user interviews (Phase 1)
│   ├── creative-lens.md      # Parallel ideation lenses (Phase 3)
│   ├── prototype-builder.md  # Builds low-fidelity prototypes (Phase 4)
│   └── persona-tester.md     # Simulates usability testing (Phase 5)
├── reference/                # Technique reference files for subagents
│   ├── empathy-techniques.md
│   ├── ideation-techniques.md
│   ├── testing-heuristics.md
│   └── dschool-framework.md
└── templates/
    └── design-document.md    # Living document template
```

## Phases

| Phase | Name | Description |
|-------|------|-------------|
| 0 | Frame | Scope problem, classify type, propose personas, initialize living document |
| 1 | Empathize | Parallel persona interviews, empathy map synthesis |
| 2 | Define | POV statements, HMW questions, design principles |
| 3 | Ideate | Three creative lenses in parallel, idea shortlisting |
| 4 | Prototype | Low-fidelity prototype (HTML, Mermaid, or narrative) |
| 5 | Test | Persona usability testing, final adversarial review, handoff |

## Key Design Decisions

- **User gates between every phase** -- no auto-advancing
- **Critic subagent runs in every phase** -- adversarial review is not optional
- **Non-linear loopback** from Phase 5 to any earlier phase, preserving all artifacts
- **Hard gate on implementation** -- no code until Phase 5 is approved
- **Living document** as single source of truth, updated after every phase
