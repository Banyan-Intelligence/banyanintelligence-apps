# Repository Map

**banyanintelligence-apps** - A newly initialized repository for applications developed by Banyan Intelligence. Currently in the bootstrapping phase with minimal content.

## Project Status

This is a **brand-new repository** with only an initial commit. No application code has been added yet.

## Directory Structure

```
banyanintelligence-apps/
├── .builder_agent/          # Builder Agent configuration (untracked)
│   └── config.yaml          # Automated issue-to-PR workflow config
├── .git/                    # Git repository metadata
└── README.md                # Project documentation (placeholder)
```

## Key Files

| File | Purpose |
|------|---------|
| `README.md` | Basic project identification (2 lines) |
| `.builder_agent/config.yaml` | Configuration for Claude Builder Agent automation |

## Builder Agent Configuration

The repository is set up for automated development workflows:

- **Trigger Labels:** `builder-agent` (for issues to process)
- **Approval Required:** `approved` label
- **Branch Pattern:** `builder-agent/issue-{issue_number}`
- **Commit Pattern:** `fix(#{issue_number}): {issue_title}`
- **PR Labels:** `automated`
- **Polling Interval:** 60 seconds

## Current State

| Aspect | Status |
|--------|--------|
| Source code | None |
| Entry points | None |
| Tests | None |
| Dependencies | None |
| Tech stack | Not yet chosen |
| Documentation | Minimal placeholder |
| License | Not added |
| .gitignore | Not added |

## Git History

Single commit:
- `f5b7a11` - "Add initial README for banyanintelligence-apps" (2026-02-12)

## Notes for AI Agents

This repository is in its initial setup phase. When working on issues:

1. **No existing patterns to follow** - You'll be establishing conventions
2. **Technology stack undetermined** - May need to scaffold based on issue requirements
3. **Builder Agent active** - Issues labeled `builder-agent` + `approved` trigger automated workflows
4. **No dependencies installed** - Will need to initialize package management as needed
