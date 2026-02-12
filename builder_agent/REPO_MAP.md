# Repository Map

## Project Overview

**banyanintelligence-apps** is an application repository for Banyan Intelligence that serves as a central hub for applications and automation tooling. The repository is currently in early bootstrapping stage, with foundational infrastructure for the Builder Agent framework in place.

**Tech Stack:** Bash (installer scripts), YAML (configuration), Claude CLI (automation)

---

## Directory Structure

```
banyanintelligence-apps/
├── .builder_core/                    # Builder Agent automation configuration
│   └── config.yaml                   # Automated workflow settings
├── builder-agent-installer/          # Public installation artifacts
│   └── index.html                    # Bash installation script (served via GitHub Pages)
└── README.md                         # Project documentation (placeholder)
```

---

## Key Files

### `/.builder_core/config.yaml`
**Purpose:** Configure Claude Builder Agent automated workflows

**Responsibilities:**
- Issue filtering and automation triggers (requires `builder-agent` + `approved` labels)
- Branch naming: `builder-agent/issue-{issue_number}`
- Commit templates: `fix(#{issue_number}): {issue_title}`
- PR automation with `automated` label
- Claude CLI integration with 600-second timeout

### `/builder-agent-installer/index.html`
**Purpose:** Distribution artifact for builder-agent tool installation

**Features:**
- OS detection (macOS, Linux, Windows)
- CPU architecture detection (amd64, arm64)
- GitHub release fetching and downloading
- Installation path: `~/.banyan/apps`
- Environment variable setup guidance

**Usage:** `curl -fsSL https://[domain]/builder-agent-installer | bash`

### `/README.md`
**Purpose:** Project identification (currently minimal placeholder)

---

## Entry Points

| Entry Point | Purpose |
|-------------|---------|
| GitHub Issues API | Automated workflow trigger via builder-agent polling |
| Installation Script | Direct curl download for builder-agent tool |
| Git Repository | Main branch at `origin/main` |

---

## Patterns & Conventions

### Naming Conventions
- **Branches:** `builder-agent/issue-{issue_number}`
- **Commits:** `fix(#{issue_number}): {issue_title}` (conventional commits)
- **Config Directories:** Hidden with dot prefix (`.builder_core`)

### Workflow Pattern
1. Create GitHub issue with `builder-agent` label
2. Add `approved` label to trigger automation
3. Builder Agent creates branch, implements fix, opens PR
4. PR is labeled `automated` for tracking

### Installation Convention
- Tools installed to `~/.banyan/apps`
- Distribution via GitHub Pages + curl pattern

---

## Current State

| Aspect | Status |
|--------|--------|
| Source Code | None (infrastructure/template repo) |
| Applications | Structure ready for onboarding |
| Tests | Not applicable yet |
| Dependencies | Bash, curl, tar (installer only) |
| CI/CD | Builder Agent provides automation |
| License | Not yet added |
| .gitignore | Not yet added |

---

## Git History

```
45744ac - name migration (.builder_agent → .builder_core)
488c219 - Merge PR #3: builder-agent/issue-2
afe59ab - fix(#2): Add app installation for builder-agent
8541ba7 - Merge PR #1: builder-agent/initialization
d9d11a9 - chore: initialize builder-agent configuration
f5b7a11 - Add initial README
```

---

## Notes for AI Agents

1. **No existing application code** - This is an infrastructure repository establishing conventions
2. **Builder Agent active** - Issues with `builder-agent` + `approved` labels trigger automated workflows
3. **Multi-app ready** - Structure supports multiple applications, currently only installer tooling exists
4. **GitHub Pages distribution** - `builder-agent-installer/index.html` is served publicly
5. **Recent migration** - Directory renamed from `.builder_agent/` to `.builder_core/`
