# Gemini CLI Repo Scripts

> Scripts for repository management, documentation generation, and Git automation using Gemini CLI.

---

## 🎯 Overview

This repository contains production automation tools for managing the Dinaverse infrastructure ecosystem. It handles:

- **Repository orchestration** — Automated initialization, branching, synchronization
- **Documentation generation** — AI-powered README and technical documentation
- **Project organization** — Standardized directory structures and templates
- **Git workflows** — Streamlined commit, push, and sync operations

**Status:** ✅ Active — Automating repository management

---

## 🚀 Core Components

### 1. **Repository Orchestrator** (`repo-orchestrator.js`)

Automates Git repository initialization and management.

**Features:**
- Initialize new repositories with standardized structure
- Create and manage branches
- Commit changes with AI-generated messages
- Push to remote with verification
- Sync forked repositories

**Usage:**

```bash
node repo-orchestrator.js \
  --action create \
  --repo-name my-new-project \
  --template infrastructure
```

### 2. **Documentation Generator** (`doc-generator.js`)

Uses Gemini CLI to generate professional README files and technical documentation.

**Features:**
- Analyze existing code/structure
- Generate contextual README content
- Create API documentation
- Build deployment guides
- Generate changelog entries

**Usage:**

```bash
node doc-generator.js \
  --source /path/to/project \
  --output README.md \
  --style professional \
  --include-deployment-guide
```

### 3. **Gemini CLI Bridge** (`gemini-bridge.js`)

Direct interface to Gemini AI for autonomous decision-making.

**Features:**
- Query Gemini for code analysis
- Generate structured documentation
- Analyze repository requirements
- Recommend project structure
- Create technical specifications

**Usage:**

```bash
node gemini-bridge.js \
  --prompt "Analyze this repo and suggest improvements" \
  --input /path/to/repo \
  --output suggestions.md
```

### 4. **Git Workflow Manager** (`git-workflow.js`)

Handles complex Git operations and synchronization.

**Features:**
- Create feature branches
- Manage merge requests
- Sync repositories
- Handle conflict resolution
- Maintain clean commit history

**Usage:**

```bash
node git-workflow.js \
  --action sync \
  --repo Dinaverse/infrastructure \
  --branch main \
  --verify-integrity
```

---

## 📂 Repository Structure

```
ai-workflow-automation/
├── README.md                          (this file)
├── lib/
│   ├── repo-orchestrator.js          Repository management
│   ├── doc-generator.js              Documentation automation
│   ├── gemini-bridge.js              Gemini AI interface
│   ├── git-workflow.js               Git operations
│   └── utils/
│       ├── logger.js                 Logging utilities
│       ├── error-handler.js          Error handling
│       └── validators.js             Input validation
├── templates/
│   ├── infrastructure/               Infrastructure project template
│   ├── documentation/                Documentation project template
│   └── security/                     Security automation template
├── examples/
│   ├── create-repo.sh                Create new repo example
│   ├── generate-docs.sh              Generate documentation example
│   └── sync-infrastructure.sh        Sync infrastructure example
├── config/
│   ├── defaults.json                 Default configurations
│   └── gemini-config.json            Gemini CLI settings
└── tests/
    ├── repo-orchestrator.test.js
    ├── doc-generator.test.js
    └── git-workflow.test.js
```

---

## ⚙️ Configuration

### Environment Variables

```bash
# Gemini CLI Authentication
GEMINI_API_KEY=your-api-key
GEMINI_MODEL=gemini-2.0-flash

# Git Configuration
GIT_USER_NAME=Dina
GIT_USER_EMAIL=96961723+Dinaverse@users.noreply.github.com
GH_TOKEN=your-github-token

# Logging
LOG_LEVEL=info
LOG_FILE=./logs/automation.log
```

### Configuration File (`config/defaults.json`)

```json
{
  "repositories": {
    "owner": "Dinaverse",
    "default_branch": "main",
    "protected_branches": ["main", "develop"]
  },
  "documentation": {
    "style": "professional",
    "include_examples": true,
    "include_architecture": true
  },
  "git": {
    "auto_commit": true,
    "commit_message_style": "conventional",
    "push_verify": true
  },
  "gemini": {
    "model": "gemini-2.0-flash",
    "temperature": 0.7,
    "max_tokens": 4096
  }
}
```

---

## 🔗 Integration Points

This automation framework integrates with:

| System | Purpose | Integration |
|--------|---------|-------------|
| **Gemini CLI** | AI analysis & generation | Direct API calls |
| **GitHub API** | Repository management | Octokit SDK |
| **Docker** | Container orchestration | Docker Compose templates |
| **n8n** | Workflow automation | Webhook triggers |
| **Sovereign Lab** | Infrastructure management | Direct SSH execution |

---

## 📖 Usage Examples

### Create a New Infrastructure Repository

```bash
node lib/repo-orchestrator.js \
  --action create \
  --repo-name sovereign-new-project \
  --template infrastructure \
  --description "New sovereign infrastructure component" \
  --auto-init
```

### Generate Documentation for Existing Project

```bash
node lib/doc-generator.js \
  --source /home/dina/projects/my-project \
  --output README.md \
  --style professional \
  --include-deployment-guide \
  --include-architecture-diagram
```

### Analyze Repository and Get Improvements

```bash
node lib/gemini-bridge.js \
  --prompt "Analyze this repository structure and suggest improvements for security and performance" \
  --input /path/to/repo \
  --output analysis.md \
  --focus security,performance
```

### Sync Multiple Repositories

```bash
node lib/git-workflow.js \
  --action sync-multiple \
  --repos-file repos-list.txt \
  --branch main \
  --verify-integrity \
  --auto-resolve-conflicts
```

---

## 🛡️ Security

- **API Keys:** Stored in environment variables, never committed
- **Git Tokens:** Rotated regularly via GitHub Settings
- **SSH Keys:** Passphrase-protected, used for secure Git operations
- **Audit Logging:** All operations logged with timestamps and actor information

---

## 🔄 Workflow Examples

### Automated Weekly Sync

```bash
# Runs every Sunday at 2 AM via cron
0 2 * * 0 /usr/bin/node /opt/ai-workflow-automation/lib/git-workflow.js \
  --action sync-all-repos \
  --branch main \
  --verify-integrity
```

### Documentation Auto-Generation on Release

```bash
# Triggered by GitHub Actions on release tag
node lib/doc-generator.js \
  --source . \
  --output README.md \
  --style professional \
  --include-changelog \
  --version ${{ github.ref }}
```

---

## 🤝 Related Projects

| Repository | Purpose |
|------------|---------|
| [Dinaverse](https://github.com/Dinaverse/Dinaverse) | Master landing page & portfolio |
| [sovereign-ai-infrastructure](https://github.com/Dinaverse/sovereign-ai-infrastructure) | Infrastructure documentation |
| [n8n-automation-hub](https://github.com/Dinaverse/n8n-automation-hub) | Workflow definitions |
| [cybersecurity-lab-automation](https://github.com/Dinaverse/cybersecurity-lab-automation) | Security automation |

---

## 📝 License & Attribution

This automation framework is part of the Dinaverse sovereign lab ecosystem.

*Autonomous by design. Documented by AI. Deployed with confidence.*
