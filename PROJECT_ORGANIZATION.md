# Powered Parachute Flight School - Project Organization

**Last Updated:** November 8, 2025
**GitHub Project:** https://github.com/users/joel-wehr/projects/1

---

## 📁 Directory Structure

### Local Organization

```
C:\Users\joelw\Documents\GitHub\
└── ppc-flight-school\                    ← All PPC repos together
    ├── ppc-knowledgebase\                ← Git repo
    └── ppc-training-platform\            ← Git repo
```

**Key Principle:** All PPC Flight School repositories are contained in ONE parent folder for easy navigation and organization.

---

## 🗂️ Repository Details

### 1. ppc-knowledgebase (PUBLIC)

**Purpose:** Training content and documentation
**Location:** `C:\Users\joelw\Documents\GitHub\ppc-flight-school\ppc-knowledgebase\`
**GitHub:** https://github.com/joel-wehr/ppc-knowledgebase

**Contents:**
- `training_content/` - 11 training modules (119,000 words)
  - 01_foundations
  - 02_regulations
  - 03_weather
  - 04_aircraft_systems
  - 05_flight_operations
  - 06_emergency_procedures
  - 07_practical_skills
  - 08_advanced_topics
  - 09_maintenance
  - 10_cross_country
  - resources/
- `CUSTOM_TRAINING_PLATFORM_SPECIFICATION.md` - Technical platform spec
- `INTERACTIVE_COURSE_PLATFORM_ANALYSIS.md` - Platform analysis
- `TRAINING_CONTENT_SUMMARY.md` - Content summary
- `Powrachute-Pegasus-POH.pdf` - Reference material

**Status:** ✅ Complete (v1.0)

---

### 2. ppc-training-platform (PRIVATE)

**Purpose:** AI-enhanced web training platform
**Location:** `C:\Users\joelw\Documents\GitHub\ppc-flight-school\ppc-training-platform\`
**GitHub:** https://github.com/joel-wehr/ppc-training-platform

**Planned Structure:**
```
ppc-training-platform/
├── frontend/          # Next.js 14 + React + TypeScript
├── backend/           # FastAPI + Python + PostgreSQL
├── infrastructure/    # AWS CDK (TypeScript)
├── shared/            # Shared types
├── docs/              # Documentation
└── docker-compose.yml # Local development
```

**Tech Stack:**
- **Frontend:** Next.js 14, TypeScript, Tailwind CSS, Shadcn/ui
- **Backend:** FastAPI, PostgreSQL 16+, SQLAlchemy, Redis
- **AI:** Claude API, pgvector embeddings
- **Infrastructure:** AWS (CloudFront, ECS, RDS, Lambda)

**Status:** 🎯 Planning Phase (Milestone: v1.0 MVP - Mar 31, 2026)

---

## 🔗 GitHub Project Management

### Project Board

**URL:** https://github.com/users/joel-wehr/projects/1

**Workflow:**
```
Todo → In Progress → Done
```

**All issues from all repositories automatically appear in this board.**

### Labels (Across All Repos)

| Label | Color | Purpose |
|-------|-------|---------|
| `content` | Blue | Training material updates |
| `mobile` | Purple | Mobile app features |
| `web-platform` | Dark Blue | Training platform features |
| `ai` | Yellow | AI integration tasks |
| `infrastructure` | Indigo | AWS/DevOps/Infrastructure |
| `documentation` | Green | Documentation updates |

### Milestones

| Repository | Milestone | Due Date | Status |
|------------|-----------|----------|--------|
| ppc-knowledgebase | v1.0 - Knowledge Base Complete | - | ✅ CLOSED |
| ppc-training-platform | v1.0 - Platform MVP | Mar 31, 2026 | 🎯 OPEN |

---

## 🚀 Development Workflow

### Starting Work

1. **Pick an issue** from the project board: https://github.com/users/joel-wehr/projects/1
2. **Move to "In Progress"** (drag & drop on board)
3. **Navigate to local repo:**
   ```bash
   cd "C:\Users\joelw\Documents\GitHub\ppc-flight-school\REPO_NAME"
   ```
4. **Create feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

### Making Changes

```bash
# Make your changes
# ... edit files ...

# Stage and commit
git add .
git commit -m "Your commit message"

# Push to GitHub
git push origin feature/your-feature-name
```

### Creating Pull Requests

```bash
# Using GitHub CLI
gh pr create --title "Your PR title" --body "Description"

# Or via web: https://github.com/joel-wehr/REPO_NAME/pulls
```

### Completing Work

1. **Merge PR** (via GitHub web or CLI)
2. **Close issue:** Issue automatically moves to "Done" if linked to PR
3. **Delete branch:**
   ```bash
   git checkout main
   git pull
   git branch -d feature/your-feature-name
   ```

---

## 📝 GitHub CLI Quick Reference

### Issues

```bash
# Create issue
gh issue create --repo joel-wehr/ppc-knowledgebase --title "..." --label "content"

# List issues
gh issue list --repo joel-wehr/ppc-knowledgebase

# View issue
gh issue view 5 --repo joel-wehr/ppc-knowledgebase

# Close issue
gh issue close 5 --repo joel-wehr/ppc-knowledgebase
```

### Pull Requests

```bash
# Create PR (from current branch)
gh pr create --title "..." --body "..."

# List PRs
gh pr list

# View PR
gh pr view 3

# Merge PR
gh pr merge 3
```

### Repositories

```bash
# View repo on GitHub
gh repo view joel-wehr/ppc-knowledgebase --web

# Clone repo
gh repo clone joel-wehr/ppc-knowledgebase

# Check repo status
gh repo view joel-wehr/ppc-knowledgebase
```

---

## 🎯 Current Project Status

### ✅ Completed

**Infrastructure:**
- ✅ All GitHub repositories created
- ✅ GitHub Project board configured and linked
- ✅ Consistent labels across all repos
- ✅ Milestones defined
- ✅ SSH authentication configured
- ✅ Local directory structure organized

**ppc-knowledgebase:**
- ✅ 119,000 words of training content (11 modules)
- ✅ Platform specifications (70,000+ words)
- ✅ All reference materials organized

### 🎯 Planned

**ppc-training-platform:**
- Issue #1: Set up Next.js frontend foundation
- Issue #2: Set up FastAPI backend with PostgreSQL
- Issue #3: Integrate Claude API for AI chat tutor

**ppc-knowledgebase:**
- Issue #1: Create scenario-based assessment modules

---

## 🔍 Finding Things

### By Type

**Training Content:**
```
ppc-flight-school/ppc-knowledgebase/training_content/
```

**Mobile App Code:**
```
ppc-pilot-ios/        # Native iOS app (Swift / SwiftUI)
ppc-pilot-android/    # Native Android app (Kotlin / Jetpack Compose)
```

**Platform Specifications:**
```
ppc-flight-school/ppc-knowledgebase/CUSTOM_TRAINING_PLATFORM_SPECIFICATION.md
ppc-flight-school/ppc-knowledgebase/INTERACTIVE_COURSE_PLATFORM_ANALYSIS.md
```

### By Task

**Want to add training content?**
- Repo: `ppc-knowledgebase`
- Location: `ppc-flight-school/ppc-knowledgebase/training_content/`
- Label: `content`

**Want to add mobile features?**
- Repos: `ppc-pilot-ios` (Swift/SwiftUI), `ppc-pilot-android` (Kotlin/Compose)
- Label: `mobile`

**Want to build web platform?**
- Repo: `ppc-training-platform`
- Location: `ppc-flight-school/ppc-training-platform/`
- Label: `web-platform`

---

## 🏗️ Best Practices

### Commit Messages

**Good:**
```
Add weather integration to flight log

- Integrate AviationWeather.gov API
- Display METAR data on flight log page
- Cache weather data for 30 minutes
- Add loading states and error handling

Fixes #5
```

**Bad:**
```
updates
```

### Branch Naming

```
feature/weather-integration
feature/ai-chat-tutor
fix/flight-log-crash
fix/ios-deployment
infra/aws-setup
docs/update-readme
```

### Issue Naming

**Good:** "Add weather integration to flight log page"
**Bad:** "Weather stuff"

---

## 🗑️ Archived & Removed

### Old Folders (Cleaned Up)

The following duplicate/old folders have been removed:
- ❌ `Documents\GitHub\powered-parachute` (orphaned)
- ❌ `Documents\GitHub\powered-parachute-aws` (orphaned)
- ❌ `Documents\GitHub\ppc-knowledgebase` (duplicate)
- ❌ `Documents\GitHub\ppc-training-platform` (duplicate)
- ❌ `Documents\Projects\PPC-knowledgebase` (moved to GitHub folder)

### Old Repositories (Archived)

33 old repositories have been archived and hidden from the main view:
- Electric Imp projects
- IoT projects
- Pitchfork projects
- Eagle libraries
- etc.

**Access archived repos:** https://github.com/joel-wehr?tab=repositories&q=&type=archived

---

## 📚 Additional Resources

### Documentation

- **This file:** Project organization and workflows
- **Training content index:** `README.md` in `training_content/`
- **Platform specs:** `CUSTOM_TRAINING_PLATFORM_SPECIFICATION.md`

### Links

- **GitHub Project Board:** https://github.com/users/joel-wehr/projects/1
- **ppc-knowledgebase:** https://github.com/joel-wehr/ppc-knowledgebase
- **ppc-training-platform:** https://github.com/joel-wehr/ppc-training-platform

---

## 🆘 Common Tasks

### Pull latest changes from all repos

```bash
cd "C:\Users\joelw\Documents\GitHub\ppc-flight-school\ppc-knowledgebase" && git pull
cd "C:\Users\joelw\Documents\GitHub\ppc-flight-school\ppc-training-platform" && git pull
```

### Check status of all repos

```bash
cd "C:\Users\joelw\Documents\GitHub\ppc-flight-school\ppc-knowledgebase" && git status
cd "C:\Users\joelw\Documents\GitHub\ppc-flight-school\ppc-training-platform" && git status
```

### Open project board

```bash
# Via GitHub CLI
gh project view 1 --owner joel-wehr --web

# Or just navigate to:
# https://github.com/users/joel-wehr/projects/1
```

---

**Everything is organized and ready to build!** 🚁✨

Start at the project board: https://github.com/users/joel-wehr/projects/1
