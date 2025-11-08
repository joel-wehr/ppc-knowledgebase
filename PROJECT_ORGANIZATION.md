# Powered Parachute Flight School - Project Organization

**Last Updated:** November 8, 2025
**GitHub Project:** https://github.com/users/joel-wehr/projects/1

---

## Overview

This document explains how the Powered Parachute Flight School project is organized across multiple repositories and managed through a single GitHub Project board.

---

## Repository Structure

### Three Main Repositories

| Repository | Purpose | Tech Stack | Status |
|------------|---------|------------|--------|
| [**ppc-knowledgebase**](https://github.com/joel-wehr/ppc-knowledgebase) | Training content & docs | Markdown, PDFs | ✅ Complete |
| [**ppc-mobile-app**](https://github.com/joel-wehr/ppc-mobile-app) | Flight log mobile app | .NET MAUI 9 | 🚧 In Progress |
| [**ppc-training-platform**](https://github.com/joel-wehr/ppc-training-platform) | Web training platform | Next.js + FastAPI | 🎯 Planning |

---

## Local File Organization

### Repository Locations

```
C:\Users\joelw\Documents\
├── Projects\
│   └── PPC-knowledgebase\          # Knowledge base repository
│       ├── training_content\
│       ├── platform-specs\
│       └── reference-materials\
│
└── GitHub\
    ├── ppc-mobile-app\              # Mobile app repository
    │   ├── src\
    │   ├── Models\
    │   ├── Views\
    │   └── Services\
    │
    └── ppc-training-platform\       # Training platform repository
        ├── frontend\
        ├── backend\
        └── infrastructure\
```

### Why Two Different Locations?

- **`Documents\Projects\`** - Knowledge base (content-focused, already existed here)
- **`Documents\GitHub\`** - Code repositories (development-focused)

Both are git repositories and pushed to GitHub.

---

## GitHub Project Management

### Project Board

**URL:** https://github.com/users/joel-wehr/projects/1

**Workflow:**
```
Todo → In Progress → Done
```

**Custom Fields:**
- **Team** - Squad 1, Squad 2, Squad 3
- **Start Date** - When work begins
- **Target Date** - Expected completion

### Labels Across All Repos

| Label | Color | Purpose |
|-------|-------|---------|
| `content` | Blue | Training material updates |
| `mobile` | Purple | Mobile app features |
| `web-platform` | Dark Blue | Training platform features |
| `ai` | Yellow | AI integration tasks |
| `infrastructure` | Indigo | AWS/DevOps/Infrastructure |
| `documentation` | Green | Documentation updates |

### Milestones

**ppc-knowledgebase:**
- ✅ v1.0 - Knowledge Base Complete (CLOSED)

**ppc-mobile-app:**
- 🎯 v1.0 - Mobile App Launch (Due: Dec 31, 2025)

**ppc-training-platform:**
- 🎯 v1.0 - Platform MVP (Due: Mar 31, 2026)

---

## Working with the Project

### Creating Issues

Issues automatically appear in the project board when created in any of the 3 repositories.

**Example workflow:**
```bash
# Create issue in mobile app repo
gh issue create --repo joel-wehr/ppc-mobile-app \
  --title "Add weather integration" \
  --body "Integrate AviationWeather.gov API" \
  --label "mobile" \
  --milestone "v1.0 - Mobile App Launch"

# Issue automatically appears in project board as "Todo"
```

### Moving Issues Through Workflow

1. **Todo** - Issue created, not started
2. **In Progress** - Actively working on it
3. **Done** - Completed and closed

Issues can be dragged between columns on the project board.

### Assigning Work

Issues can be assigned to:
- **Assignees** - Specific people
- **Team** - Squad 1, Squad 2, or Squad 3 (custom field)

---

## Current Project Status

### ✅ Completed

**ppc-knowledgebase:**
- 119,000 words of training content (11 modules)
- Platform specifications (70,000+ words)
- All reference materials organized

**ppc-mobile-app:**
- .NET MAUI app with checklists
- Flight logging system
- SQLite database
- iOS/Android support

**Infrastructure:**
- All 3 repos created and pushed to GitHub
- GitHub Project board configured
- Consistent labels across repos
- Milestones defined
- Initial issues created

### 🚧 In Progress

**ppc-mobile-app:**
- Issue #1: Deploy iOS app to TestFlight

### 🎯 Planned

**ppc-training-platform:**
- Issue #1: Set up Next.js frontend
- Issue #2: Set up FastAPI backend
- Issue #3: Integrate Claude API

**ppc-knowledgebase:**
- Issue #1: Create scenario-based assessments

---

## Development Workflow

### 1. Pick an Issue

Go to project board: https://github.com/users/joel-wehr/projects/1

Filter by:
- Label (what you want to work on)
- Repository (which codebase)
- Status (available work in "Todo")

### 2. Move to "In Progress"

Drag issue to "In Progress" column or:
```bash
# Via GitHub website - easiest
# Or programmatically with gh CLI
```

### 3. Work Locally

```bash
# Navigate to repository
cd "C:\Users\joelw\Documents\GitHub\ppc-mobile-app"

# Create feature branch
git checkout -b feature/weather-integration

# Make changes, commit
git add .
git commit -m "Add weather integration"

# Push
git push origin feature/weather-integration
```

### 4. Create Pull Request

```bash
gh pr create --title "Add weather integration" --body "Implements issue #5"
```

### 5. Close Issue

When work is complete:
```bash
gh issue close 5 --comment "Completed in PR #12"
```

Issue automatically moves to "Done" column.

---

## Repository Details

### ppc-knowledgebase

**Purpose:** Training content and documentation

**Contents:**
- `training_content/` - 11 training modules
- `platform-specs/` - Technical specifications
- `reference-materials/` - Powrachute POH, etc.

**No code** - Just markdown and PDFs.

### ppc-mobile-app

**Purpose:** .NET MAUI mobile app for iOS/Android

**Contents:**
- `Models/` - Data models
- `ViewModels/` - MVVM view models
- `Views/` - XAML pages
- `Services/` - Business logic
- `Platforms/` - iOS, Android, Windows specific code

**Tech:** .NET MAUI 9, SQLite, C#

### ppc-training-platform

**Purpose:** AI-enhanced web training platform

**Structure:**
```
ppc-training-platform/
├── frontend/          # Next.js 14
├── backend/           # FastAPI (Python)
├── infrastructure/    # AWS CDK
├── shared/            # Shared types
└── docs/              # Documentation
```

**Tech:** Next.js, FastAPI, PostgreSQL, Redis, AWS

---

## GitHub CLI Quick Reference

### Issues

```bash
# Create issue
gh issue create --repo joel-wehr/REPO_NAME --title "..." --label "..."

# List issues
gh issue list --repo joel-wehr/REPO_NAME

# Close issue
gh issue close NUMBER --repo joel-wehr/REPO_NAME
```

### Pull Requests

```bash
# Create PR
gh pr create --title "..." --body "..."

# List PRs
gh pr list

# Merge PR
gh pr merge NUMBER
```

### Projects

```bash
# View project
gh project view 1 --owner joel-wehr

# All issues managed via web UI: https://github.com/users/joel-wehr/projects/1
```

---

## Best Practices

### Issue Naming

- **Good:** "Add weather integration to flight log page"
- **Bad:** "Weather stuff"

### Labels

Use multiple labels for cross-cutting concerns:
- `web-platform,ai` - AI features in web platform
- `mobile,infrastructure` - Mobile app DevOps

### Commits

```bash
# Good
git commit -m "Add weather integration

- Integrate AviationWeather.gov API
- Display METAR data on flight log
- Cache weather data for 30 minutes

Fixes #5"

# Bad
git commit -m "updates"
```

### Branches

```bash
# Feature branches
feature/weather-integration
feature/ai-chat-tutor

# Bug fixes
fix/flight-log-crash
fix/ios-deployment

# Infrastructure
infra/aws-setup
infra/ci-cd-pipeline
```

---

## Archived Repositories

All previous repositories (33 total) have been archived:
- Electric Imp projects
- IoT projects
- Pitchfork projects
- Eagle libraries
- etc.

**Status:** Hidden from main view, still accessible if needed
**Access:** https://github.com/joel-wehr?tab=repositories&q=&type=archived

---

## Questions?

- **Project Board:** https://github.com/users/joel-wehr/projects/1
- **Knowledge Base:** https://github.com/joel-wehr/ppc-knowledgebase
- **Mobile App:** https://github.com/joel-wehr/ppc-mobile-app
- **Training Platform:** https://github.com/joel-wehr/ppc-training-platform

---

**Everything is connected through the GitHub Project board. Start there!**
