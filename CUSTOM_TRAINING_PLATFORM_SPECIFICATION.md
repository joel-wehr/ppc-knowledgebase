# Custom Powered Parachute Training Platform
## Complete Technical Specification for Bespoke Open-Source Learning System

**Date**: November 8, 2025
**Version**: 1.0
**Purpose**: Build a modern, AI-enhanced, evidence-based training platform using 100% open-source technologies

---

## Executive Summary

This document provides complete technical specifications for building a custom, bespoke training platform specifically designed for powered parachute pilot education. The platform will leverage modern open-source technologies, implement evidence-based learning methodologies, and integrate AI for personalized, adaptive learning experiences.

**Key Objectives**:
1. Create engaging, interactive microlearning experiences
2. Implement spaced repetition and active recall automatically
3. Provide AI-powered personalization and tutoring
4. Track detailed learner progress and competencies
5. Deliver mobile-responsive, accessible content
6. Maintain complete ownership and control of platform and data

**Technology Philosophy**: 100% open source, modern, scalable, maintainable

**Development Approach**: Agile, iterative, MVP-first

**Timeline**: 12-16 weeks to production-ready MVP

**Team Size**: 1-2 developers (or solo with 20-30 hours/week)

---

## Table of Contents

1. [Technology Stack](#technology-stack)
2. [System Architecture](#system-architecture)
3. [Database Schema](#database-schema)
4. [API Design](#api-design)
5. [Frontend Components](#frontend-components)
6. [Backend Services](#backend-services)
7. [AI Integration](#ai-integration)
8. [Learning Features](#learning-features)
9. [Development Roadmap](#development-roadmap)
10. [Deployment Strategy](#deployment-strategy)
11. [Cost Estimation](#cost-estimation)

---

## Part 1: Technology Stack

### Frontend Technology Stack

#### **Framework: Next.js 14+ (React)**
**Why Next.js**:
- Server-side rendering (SSR) for better SEO and performance
- Static site generation (SSG) for content pages
- API routes (built-in backend endpoints)
- File-based routing (intuitive organization)
- Automatic code splitting (faster load times)
- Image optimization (automatic responsive images)
- TypeScript support (type safety)
- Excellent developer experience
- **40% faster prototyping** than vanilla React
- Large, active community

**Alternatives Considered**:
- **Vue/Nuxt**: Good, but smaller ecosystem for learning tools
- **SvelteKit**: Excellent performance, smaller community
- **Django templates**: Server-side, less interactive

**Decision**: Next.js provides the best balance of performance, developer experience, and ecosystem.

#### **UI Component Library: Shadcn/ui + Tailwind CSS**
**Why Shadcn/ui**:
- Beautiful, accessible components
- Built on Radix UI (accessibility primitives)
- Fully customizable (copy into your codebase)
- Tailwind CSS integration (utility-first styling)
- Type-safe with TypeScript
- No npm dependency bloat (you own the code)

**Tailwind CSS**:
- Utility-first CSS framework
- Rapid UI development
- Consistent design system
- Responsive design built-in
- Optimized production builds (tiny CSS files)

**Alternatives Considered**:
- **Material UI**: Heavy, opinionated
- **Chakra UI**: Good, but less customizable
- **Bootstrap**: Dated, less modern

**Decision**: Shadcn/ui + Tailwind provides maximum flexibility and modern aesthetics.

#### **State Management: Zustand + React Query**
**Zustand** (Simple Global State):
- Lightweight (1KB)
- Simple API
- No boilerplate
- TypeScript friendly

**React Query** (Server State):
- Automatic caching
- Background refetching
- Optimistic updates
- Infinite scroll support
- Perfect for API data

**Alternatives**:
- **Redux**: Too much boilerplate
- **Recoil**: Good but less mature
- **Context API**: Good for simple cases, doesn't scale

**Decision**: Zustand for client state, React Query for server state = best of both worlds.

#### **Forms: React Hook Form + Zod**
- **React Hook Form**: Performant, minimal re-renders
- **Zod**: TypeScript-first schema validation
- Excellent error handling
- Easy integration

#### **Rich Text Editor: TipTap**
- Open source (MIT license)
- Based on ProseMirror
- Highly customizable
- Markdown support
- Collaborative editing capable
- Perfect for course content authoring

#### **Interactive Content: Custom Components**
- **Drag-and-Drop**: react-dnd or @dnd-kit
- **Quiz Engine**: Custom-built with React Hook Form
- **Scenarios**: Custom branching logic components
- **Progress Bars**: Custom SVG animations
- **Charts**: Recharts or Chart.js

#### **Video Player: Video.js**
- Open source
- Plugin ecosystem
- HLS/DASH support
- Responsive
- Analytics integration

---

### Backend Technology Stack

#### **Framework: FastAPI (Python)**
**Why FastAPI**:
- Extremely fast (on par with Node.js)
- Modern Python (async/await)
- Automatic API documentation (OpenAPI/Swagger)
- Type hints with Pydantic (validation)
- Excellent for AI/ML integration (Python ecosystem)
- WebSocket support (real-time features)
- Background tasks (email, processing)
- Easy to test
- Growing ecosystem

**Alternatives Considered**:
- **Django**: Batteries included, but heavier, less modern async
- **Flask**: Lightweight, but too minimal for this scale
- **Node.js/Express**: Good, but Python better for AI integration
- **Next.js API routes**: Could work, but separate backend cleaner

**Decision**: FastAPI provides best performance, AI integration, and developer experience.

#### **Database: PostgreSQL 16+**
**Why PostgreSQL**:
- Open source (PostgreSQL license)
- **Superior for complex queries** (learning analytics)
- JSONB support (flexible data storage)
- Full-text search (content search)
- Excellent indexing (performance)
- ACID compliance (data integrity)
- Partitioning (scalability)
- Most admired database in 2025
- **45% market share** (surpassed MySQL)
- Rich extension ecosystem

**Key Features for Our Use Case**:
- Store course content, user progress, quiz data
- JSONB for flexible metadata (course settings, AI context)
- Full-text search for content discovery
- Analytics queries (student performance, knowledge gaps)
- Row-level security (multi-tenancy if needed)

**Alternatives**:
- **MySQL**: Fast reads, but less feature-rich
- **MongoDB**: NoSQL, but we need relational data
- **SQLite**: Too limited for production

**Decision**: PostgreSQL is the clear winner for scalability, features, and performance.

#### **ORM: SQLAlchemy + Alembic**
- **SQLAlchemy**: Powerful Python ORM
- **Alembic**: Database migrations
- Type hints support
- Async support (with asyncpg)
- Complex queries when needed

#### **Caching: Redis**
- In-memory cache
- Session storage
- Rate limiting
- Pub/sub for real-time features
- Job queue (background tasks)

#### **Task Queue: Celery (or ARQ for simpler)**
- Background jobs (email notifications, analytics)
- Scheduled tasks (spaced repetition reminders)
- Async processing (AI calls, video encoding)

**Alternatives**:
- **ARQ**: Simpler, Redis-based, async-native
- **RQ**: Simple but synchronous
- **Decision**: Start with ARQ, migrate to Celery if needed

#### **File Storage**
**Development**: Local filesystem
**Production**: AWS S3 or DigitalOcean Spaces (S3-compatible)
- Store videos, images, PDFs
- CDN integration (CloudFront or DigitalOcean CDN)

---

### AI Integration Stack

#### **Primary AI: Claude API (Anthropic)**
**Why Claude**:
- **200K context window** (can ingest entire training corpus)
- Excellent instruction following
- Safe and helpful responses
- Markdown formatting native
- Latest models (Claude 3.5 Sonnet, Claude 3 Opus)
- Streaming responses
- Reasonable pricing

**Use Cases**:
- Chat tutor (Q&A on training content)
- Scenario generation
- Personalized feedback
- Adaptive quiz question generation
- Progress analysis and recommendations

**Alternatives**:
- **OpenAI GPT-4**: Excellent, but smaller context (128K)
- **Open-source models** (Llama 3, Mistral): Could self-host
- **Decision**: Start with Claude API, add self-hosted option later

#### **Embeddings: OpenAI Embeddings or Sentence Transformers**
**For**: Semantic search, content recommendations, knowledge graph

**Options**:
- **OpenAI ada-002**: Best performance, low cost
- **Sentence Transformers**: Free, self-hosted
- **Decision**: OpenAI for MVP, migrate to self-hosted if needed

#### **Vector Database: pgvector (PostgreSQL extension)**
**Why pgvector**:
- Native PostgreSQL extension
- No separate vector DB needed
- Store embeddings alongside data
- Efficient similarity search
- Open source

**Alternatives**:
- **Pinecone**: Managed, but costs money
- **Weaviate**: Good, but another service to manage
- **Qdrant**: Excellent, but adds complexity
- **Decision**: pgvector keeps everything in PostgreSQL

---

### DevOps & Infrastructure

#### **Version Control: Git + GitHub**
- Source control
- Issue tracking
- CI/CD (GitHub Actions)
- Documentation (README, wiki)

#### **CI/CD: GitHub Actions**
- Automated testing
- Automated deployment
- Linting and formatting
- Database migrations

#### **Containerization: Docker + Docker Compose**
- Development consistency
- Easy deployment
- Service orchestration (frontend, backend, database, redis)

#### **Hosting Options**

**Development**:
- Local Docker containers
- PostgreSQL, Redis local instances

**Production Options** (in order of recommendation):

1. **DigitalOcean App Platform + Managed Databases** (RECOMMENDED)
   - **Pros**: Simple, affordable, includes everything
   - **Cost**: ~$50-100/month for full stack
   - **Components**:
     - App Platform (frontend + backend): $12-25/month each
     - Managed PostgreSQL: $15-30/month
     - Managed Redis: $15/month
     - Spaces (S3-compatible storage): $5/month
   - **Why**: Best balance of simplicity and cost

2. **Railway.app**
   - **Pros**: Modern, simple, generous free tier
   - **Cost**: $5-20/month to start
   - **Why**: Easy for developers, great DX

3. **Render.com**
   - **Pros**: Simple deployment, free tier
   - **Cost**: $0-50/month
   - **Why**: Good starter option

4. **Self-Hosted VPS (DigitalOcean Droplet, Linode)**
   - **Pros**: Full control, cheapest long-term
   - **Cost**: $24-48/month (4-8GB RAM)
   - **Why**: Maximum control, requires DevOps knowledge

5. **AWS (via Amplify or ECS)**
   - **Pros**: Enterprise-grade, unlimited scale
   - **Cost**: Variable, can be expensive
   - **Why**: Overkill for MVP, but ultimate scalability

**Recommended Path**: Start with Railway or Render (easy, cheap), migrate to DigitalOcean App Platform when revenue starts, consider self-hosted VPS for ultimate control later.

#### **Monitoring & Analytics**

**Application Monitoring**:
- **Sentry**: Error tracking (free tier generous)
- **Plausible or Umami**: Privacy-friendly analytics (self-hosted or $9/month)

**Performance Monitoring**:
- **Vercel Analytics** (if deploying frontend to Vercel)
- **Custom logging** to PostgreSQL

**Uptime Monitoring**:
- **UptimeRobot**: Free tier includes 50 monitors
- **Healthchecks.io**: Open source alternative

---

## Part 2: System Architecture

### High-Level Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                         CLIENT TIER                          │
│  ┌─────────────────────────────────────────────────────┐   │
│  │            Next.js Frontend (React)                 │   │
│  │  • Course viewer • Quizzes • AI chat                │   │
│  │  • Progress dashboards • Profile • Admin            │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                            │
                            │ HTTPS/WebSocket
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                      APPLICATION TIER                        │
│  ┌─────────────────────────────────────────────────────┐   │
│  │           FastAPI Backend (Python)                  │   │
│  │  • REST API • WebSocket • Background jobs           │   │
│  │  • Business logic • Authentication • AI integration │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                            │
                            │
      ┌─────────────────────┼─────────────────────┐
      │                     │                     │
      ▼                     ▼                     ▼
┌──────────────┐   ┌──────────────┐    ┌──────────────┐
│ PostgreSQL   │   │    Redis     │    │  File Store  │
│  Database    │   │    Cache     │    │ (S3/Spaces)  │
│              │   │   Sessions   │    │ Videos/PDFs  │
│ + pgvector   │   │  Job Queue   │    │    Images    │
└──────────────┘   └──────────────┘    └──────────────┘
                            │
                            ▼
                   ┌──────────────┐
                   │  Claude API  │
                   │   (External) │
                   │  AI Tutor    │
                   └──────────────┘
```

### Component Architecture

#### **Frontend Components Hierarchy**

```
app/ (Next.js 14 App Router)
├── (auth)/ - Authentication pages
│   ├── login/
│   ├── signup/
│   └── reset-password/
├── (student)/ - Student portal
│   ├── dashboard/
│   ├── courses/
│   │   └── [courseId]/
│   │       ├── lessons/
│   │       │   └── [lessonId]/
│   │       ├── quizzes/
│   │       └── progress/
│   ├── practice/ - Flashcards & spaced repetition
│   ├── ai-tutor/ - Chat interface
│   └── profile/
├── (instructor)/ - Instructor portal
│   ├── dashboard/
│   ├── courses/
│   │   └── [courseId]/
│   │       ├── edit/
│   │       ├── students/
│   │       └── analytics/
│   └── content-creator/
├── (admin)/ - Admin panel
│   ├── users/
│   ├── courses/
│   ├── analytics/
│   └── settings/
└── api/ - API routes (if needed for frontend-only features)
```

#### **Backend Services Architecture**

```
app/
├── main.py - FastAPI application entry
├── core/
│   ├── config.py - Configuration (env vars)
│   ├── security.py - Authentication, JWT
│   └── database.py - Database connection
├── models/ - SQLAlchemy models
│   ├── user.py
│   ├── course.py
│   ├── lesson.py
│   ├── quiz.py
│   ├── progress.py
│   └── flashcard.py
├── schemas/ - Pydantic schemas (API contracts)
│   ├── user.py
│   ├── course.py
│   └── ...
├── api/ - API endpoints
│   ├── v1/
│   │   ├── auth.py
│   │   ├── courses.py
│   │   ├── lessons.py
│   │   ├── quizzes.py
│   │   ├── progress.py
│   │   ├── ai_tutor.py
│   │   └── admin.py
│   └── websocket.py - Real-time features
├── services/ - Business logic
│   ├── auth_service.py
│   ├── course_service.py
│   ├── quiz_service.py
│   ├── spaced_repetition.py - SR algorithm (SM-2)
│   ├── ai_service.py - Claude integration
│   ├── analytics_service.py
│   └── notification_service.py
├── tasks/ - Background jobs (Celery/ARQ)
│   ├── email_tasks.py
│   ├── sr_reminders.py - Spaced repetition notifications
│   └── analytics_tasks.py
└── utils/
    ├── email.py
    ├── s3.py - File upload
    └── helpers.py
```

---

## Part 3: Database Schema

### Core Tables

#### **users**
```sql
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email VARCHAR(255) UNIQUE NOT NULL,
    username VARCHAR(50) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    role VARCHAR(20) DEFAULT 'student', -- student, instructor, admin
    avatar_url VARCHAR(500),
    bio TEXT,
    is_active BOOLEAN DEFAULT true,
    is_verified BOOLEAN DEFAULT false,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW(),
    last_login_at TIMESTAMP
);

CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_role ON users(role);
```

#### **courses**
```sql
CREATE TABLE courses (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    title VARCHAR(255) NOT NULL,
    slug VARCHAR(255) UNIQUE NOT NULL,
    description TEXT,
    short_description VARCHAR(500),
    difficulty VARCHAR(20), -- beginner, intermediate, advanced
    estimated_hours INTEGER,
    thumbnail_url VARCHAR(500),
    instructor_id UUID REFERENCES users(id),
    is_published BOOLEAN DEFAULT false,
    published_at TIMESTAMP,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_courses_slug ON courses(slug);
CREATE INDEX idx_courses_published ON courses(is_published);
```

#### **modules** (sections within courses)
```sql
CREATE TABLE modules (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    course_id UUID REFERENCES courses(id) ON DELETE CASCADE,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    order_index INTEGER NOT NULL,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_modules_course ON modules(course_id);
```

#### **lessons** (individual learning units - 8-12 minutes each)
```sql
CREATE TABLE lessons (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    module_id UUID REFERENCES modules(id) ON DELETE CASCADE,
    title VARCHAR(255) NOT NULL,
    slug VARCHAR(255) NOT NULL,
    content TEXT NOT NULL, -- Markdown or JSON
    lesson_type VARCHAR(20), -- video, reading, interactive, quiz
    video_url VARCHAR(500),
    duration_minutes INTEGER,
    order_index INTEGER NOT NULL,
    prerequisites JSONB, -- Array of lesson IDs that must be completed first
    learning_objectives JSONB, -- Array of learning objectives
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_lessons_module ON lessons(module_id);
CREATE INDEX idx_lessons_slug ON lessons(slug);
```

#### **quizzes**
```sql
CREATE TABLE quizzes (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    lesson_id UUID REFERENCES lessons(id) ON DELETE CASCADE,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    passing_score INTEGER DEFAULT 70, -- percentage
    time_limit_minutes INTEGER, -- NULL = no time limit
    max_attempts INTEGER, -- NULL = unlimited
    shuffle_questions BOOLEAN DEFAULT true,
    shuffle_answers BOOLEAN DEFAULT true,
    show_correct_answers BOOLEAN DEFAULT true,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);
```

#### **questions**
```sql
CREATE TABLE questions (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    quiz_id UUID REFERENCES quizzes(id) ON DELETE CASCADE,
    question_text TEXT NOT NULL,
    question_type VARCHAR(20), -- multiple_choice, true_false, fill_blank, matching
    explanation TEXT, -- Shown after answer
    points INTEGER DEFAULT 1,
    difficulty VARCHAR(20), -- easy, medium, hard
    order_index INTEGER,
    created_at TIMESTAMP DEFAULT NOW()
);
```

#### **answers**
```sql
CREATE TABLE answers (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    question_id UUID REFERENCES questions(id) ON DELETE CASCADE,
    answer_text TEXT NOT NULL,
    is_correct BOOLEAN DEFAULT false,
    order_index INTEGER,
    created_at TIMESTAMP DEFAULT NOW()
);
```

### Progress Tracking Tables

#### **enrollments**
```sql
CREATE TABLE enrollments (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    course_id UUID REFERENCES courses(id) ON DELETE CASCADE,
    enrolled_at TIMESTAMP DEFAULT NOW(),
    completed_at TIMESTAMP,
    progress_percentage INTEGER DEFAULT 0,
    last_accessed_at TIMESTAMP,
    UNIQUE(user_id, course_id)
);

CREATE INDEX idx_enrollments_user ON enrollments(user_id);
CREATE INDEX idx_enrollments_course ON enrollments(course_id);
```

#### **lesson_progress**
```sql
CREATE TABLE lesson_progress (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    lesson_id UUID REFERENCES lessons(id) ON DELETE CASCADE,
    status VARCHAR(20), -- not_started, in_progress, completed
    started_at TIMESTAMP,
    completed_at TIMESTAMP,
    time_spent_seconds INTEGER DEFAULT 0,
    UNIQUE(user_id, lesson_id)
);

CREATE INDEX idx_lesson_progress_user ON lesson_progress(user_id);
```

#### **quiz_attempts**
```sql
CREATE TABLE quiz_attempts (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    quiz_id UUID REFERENCES quizzes(id) ON DELETE CASCADE,
    started_at TIMESTAMP DEFAULT NOW(),
    completed_at TIMESTAMP,
    score INTEGER, -- percentage
    passed BOOLEAN,
    time_taken_seconds INTEGER,
    answers JSONB, -- Store user's answers for review
    created_at TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_quiz_attempts_user ON quiz_attempts(user_id);
CREATE INDEX idx_quiz_attempts_quiz ON quiz_attempts(quiz_id);
```

### Spaced Repetition Tables

#### **flashcards**
```sql
CREATE TABLE flashcards (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    lesson_id UUID REFERENCES lessons(id) ON DELETE CASCADE,
    front TEXT NOT NULL, -- Question
    back TEXT NOT NULL, -- Answer
    tags JSONB, -- Array of tags for categorization
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);
```

#### **flashcard_reviews** (SM-2 algorithm data)
```sql
CREATE TABLE flashcard_reviews (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    flashcard_id UUID REFERENCES flashcards(id) ON DELETE CASCADE,
    ease_factor FLOAT DEFAULT 2.5, -- SM-2 ease factor
    interval_days INTEGER DEFAULT 0, -- Days until next review
    repetitions INTEGER DEFAULT 0, -- Number of successful reviews
    last_reviewed_at TIMESTAMP,
    next_review_at TIMESTAMP,
    quality_rating INTEGER, -- 0-5 (SM-2 rating)
    created_at TIMESTAMP DEFAULT NOW(),
    UNIQUE(user_id, flashcard_id)
);

CREATE INDEX idx_flashcard_reviews_user ON flashcard_reviews(user_id);
CREATE INDEX idx_flashcard_reviews_next ON flashcard_reviews(next_review_at);
```

### AI & Analytics Tables

#### **ai_chat_sessions**
```sql
CREATE TABLE ai_chat_sessions (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    started_at TIMESTAMP DEFAULT NOW(),
    ended_at TIMESTAMP,
    message_count INTEGER DEFAULT 0
);
```

#### **ai_chat_messages**
```sql
CREATE TABLE ai_chat_messages (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    session_id UUID REFERENCES ai_chat_sessions(id) ON DELETE CASCADE,
    role VARCHAR(20), -- user, assistant
    content TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT NOW()
);
```

#### **learning_analytics**
```sql
CREATE TABLE learning_analytics (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    event_type VARCHAR(50), -- lesson_started, lesson_completed, quiz_passed, etc.
    event_data JSONB, -- Additional context
    created_at TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_analytics_user ON learning_analytics(user_id);
CREATE INDEX idx_analytics_type ON learning_analytics(event_type);
CREATE INDEX idx_analytics_created ON learning_analytics(created_at);
```

### Content Embeddings (for AI semantic search)

#### **content_embeddings**
```sql
CREATE TABLE content_embeddings (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    content_type VARCHAR(20), -- lesson, quiz, flashcard
    content_id UUID NOT NULL,
    content_text TEXT NOT NULL,
    embedding vector(1536), -- OpenAI ada-002 = 1536 dimensions
    created_at TIMESTAMP DEFAULT NOW()
);

-- Enable pgvector extension
CREATE EXTENSION IF NOT EXISTS vector;

-- Index for similarity search
CREATE INDEX ON content_embeddings USING ivfflat (embedding vector_cosine_ops);
```

---

## Part 4: API Design

### RESTful API Endpoints

#### **Authentication** (`/api/v1/auth`)

```
POST   /auth/register          - Create new user account
POST   /auth/login             - Login and get JWT token
POST   /auth/refresh           - Refresh access token
POST   /auth/logout            - Logout (invalidate token)
POST   /auth/forgot-password   - Request password reset
POST   /auth/reset-password    - Reset password with token
GET    /auth/me                - Get current user profile
PATCH  /auth/me                - Update current user profile
```

#### **Courses** (`/api/v1/courses`)

```
GET    /courses                - List all published courses
GET    /courses/:id            - Get course details
POST   /courses                - Create course (instructor/admin)
PATCH  /courses/:id            - Update course (instructor/admin)
DELETE /courses/:id            - Delete course (admin)
GET    /courses/:id/modules    - Get course modules
POST   /courses/:id/enroll     - Enroll in course
GET    /courses/:id/progress   - Get user's progress in course
```

#### **Lessons** (`/api/v1/lessons`)

```
GET    /lessons/:id            - Get lesson content
POST   /lessons/:id/start      - Mark lesson as started
POST   /lessons/:id/complete   - Mark lesson as completed
PATCH  /lessons/:id/progress   - Update time spent, bookmark, etc.
```

#### **Quizzes** (`/api/v1/quizzes`)

```
GET    /quizzes/:id            - Get quiz details (without answers)
POST   /quizzes/:id/start      - Start quiz attempt
POST   /quizzes/:id/submit     - Submit quiz answers
GET    /quizzes/:id/attempts   - Get user's quiz attempts
GET    /quizzes/attempts/:id   - Get specific attempt with feedback
```

#### **Spaced Repetition** (`/api/v1/flashcards`)

```
GET    /flashcards/due         - Get flashcards due for review
POST   /flashcards/:id/review  - Submit flashcard review (rating 0-5)
GET    /flashcards/stats       - Get review statistics
GET    /flashcards/upcoming    - Get upcoming review schedule
```

#### **AI Tutor** (`/api/v1/ai`)

```
POST   /ai/chat                - Send message to AI tutor
GET    /ai/sessions            - Get chat sessions
GET    /ai/sessions/:id        - Get session history
POST   /ai/generate-scenario   - Generate practice scenario
POST   /ai/explain             - Ask AI to explain a concept
```

#### **Progress & Analytics** (`/api/v1/progress`)

```
GET    /progress/dashboard     - Get dashboard overview
GET    /progress/courses/:id   - Detailed course progress
GET    /progress/streaks       - Get study streak data
GET    /progress/achievements  - Get earned badges/achievements
GET    /progress/leaderboard   - Get leaderboard rankings
```

#### **Admin** (`/api/v1/admin`)

```
GET    /admin/users            - List users
GET    /admin/analytics        - Platform-wide analytics
POST   /admin/content/import   - Import course content (from markdown)
GET    /admin/content/export   - Export course content
```

### WebSocket Endpoints

```
WS     /ws/ai-chat             - Real-time AI chat streaming
WS     /ws/notifications       - Real-time notifications
WS     /ws/progress            - Real-time progress updates
```

### Example API Request/Response

#### **POST /api/v1/quizzes/:id/submit**

**Request**:
```json
{
  "attempt_id": "uuid",
  "answers": [
    {
      "question_id": "uuid",
      "selected_answers": ["uuid1", "uuid2"]
    },
    {
      "question_id": "uuid",
      "text_answer": "Approximately 25 mph"
    }
  ],
  "time_taken_seconds": 420
}
```

**Response**:
```json
{
  "score": 85,
  "passed": true,
  "total_questions": 10,
  "correct_answers": 9,
  "results": [
    {
      "question_id": "uuid",
      "correct": true,
      "explanation": "Correct! Lift is generated by the wing's angle of attack...",
      "your_answer": "uuid1",
      "correct_answer": "uuid1"
    },
    {
      "question_id": "uuid",
      "correct": false,
      "explanation": "Not quite. PPC cruise speed is typically 25-30 mph, not 35 mph.",
      "your_answer": "35 mph",
      "correct_answer": "25-30 mph"
    }
  ],
  "recommendations": [
    "Review: Lesson 2.3 - PPC Performance Characteristics",
    "Practice: Wing aerodynamics flashcards"
  ],
  "next_steps": {
    "can_proceed": true,
    "next_lesson_id": "uuid",
    "retry_available": true
  }
}
```

---

## Part 5: Frontend Components

### Key UI Components to Build

#### **1. Lesson Viewer Component**

**Features**:
- Markdown rendering with syntax highlighting
- Embedded videos (Video.js player)
- Interactive diagrams (SVG with hotspots)
- Progress tracking (auto-save position)
- Note-taking sidebar
- Previous/Next navigation
- Table of contents sidebar
- Mobile-responsive

**Component Structure**:
```tsx
<LessonViewer>
  <LessonHeader />
  <LessonContent>
    <MarkdownRenderer />
    <VideoPlayer />
    <InteractiveDiagram />
  </LessonContent>
  <LessonSidebar>
    <TableOfContents />
    <Notes />
    <AITutorWidget />
  </LessonSidebar>
  <LessonNavigation />
  <ProgressTracker />
</LessonViewer>
```

#### **2. Quiz Component**

**Features**:
- Multiple question types
- Timer display (if timed)
- Question navigation
- Flag for review
- Immediate or end-of-quiz feedback
- Detailed explanations
- Retry option
- Progress indicator

**Component Structure**:
```tsx
<QuizAttempt>
  <QuizHeader timer={} />
  <QuestionNavigator />
  <CurrentQuestion>
    {type === 'multiple_choice' && <MultipleChoice />}
    {type === 'true_false' && <TrueFalse />}
    {type === 'fill_blank' && <FillInBlank />}
    {type === 'matching' && <Matching />}
  </CurrentQuestion>
  <QuizActions />
  {showResults && <QuizResults />}
</QuizAttempt>
```

#### **3. Flashcard Review Component (Spaced Repetition)**

**Features**:
- Flip animation
- Quality rating buttons (0-5)
- Show answer
- Keyboard shortcuts
- Progress bar (cards remaining)
- Statistics
- Skip option
- Tags filter

**Component Structure**:
```tsx
<FlashcardReview>
  <ReviewHeader stats={} />
  <FlashcardStack>
    <FlashcardItem>
      <CardFront />
      <CardBack />
      <FlipButton />
    </FlashcardItem>
  </FlashcardStack>
  <QualityRating onRate={} />
  <ReviewActions />
</FlashcardReview>
```

#### **4. AI Chat Tutor Component**

**Features**:
- Real-time streaming responses (WebSocket)
- Chat history
- Context awareness (current lesson)
- Code syntax highlighting
- Markdown formatting
- Voice input (optional)
- Suggested questions
- Clear history

**Component Structure**:
```tsx
<AIChatTutor>
  <ChatHeader />
  <MessageList>
    {messages.map(msg => (
      <Message role={msg.role} content={msg.content} />
    ))}
    {isStreaming && <StreamingMessage />}
  </MessageList>
  <SuggestedQuestions />
  <ChatInput onSend={} />
</AIChatTutor>
```

#### **5. Progress Dashboard**

**Features**:
- Course completion percentage
- Study streak calendar
- Time spent graphs
- Quiz performance charts
- Badges and achievements
- XP and level display
- Leaderboard rankings
- Goals and milestones

**Component Structure**:
```tsx
<ProgressDashboard>
  <DashboardHeader user={} />
  <Grid>
    <CourseProgressCard />
    <StudyStreakCard />
    <PerformanceChart />
    <AchievementsBadges />
    <LeaderboardWidget />
    <UpcomingReviews />
  </Grid>
</ProgressDashboard>
```

#### **6. Interactive Diagram Component**

**Features**:
- SVG-based diagrams
- Clickable hotspots
- Tooltips on hover
- Zoom and pan
- Labels show/hide
- Mobile touch support
- Step-by-step mode

**Example: Aircraft Pre-Flight Inspection**:
```tsx
<InteractiveDiagram>
  <SVGCanvas>
    <AircraftImage />
    <Hotspot id="nose_wheel" onClick={showInfo} />
    <Hotspot id="wing_riser" onClick={showInfo} />
    <Hotspot id="engine" onClick={showInfo} />
    {/* ... more hotspots ... */}
  </SVGCanvas>
  <InfoPanel>
    {selectedHotspot && <HotspotDetail />}
  </InfoPanel>
  <ProgressTracker completedHotspots={} />
</InteractiveDiagram>
```

#### **7. Branching Scenario Component**

**Features**:
- Story-like interface
- Decision points
- Multiple branches
- Feedback on choices
- Reset and retry
- Track path taken
- Show consequences

**Example: Weather Decision Scenario**:
```tsx
<BranchingScenario>
  <ScenarioHeader />
  <CurrentScene>
    <SceneDescription />
    <SceneImage />
  </CurrentScene>
  <DecisionPoints>
    {choices.map(choice => (
      <ChoiceButton onClick={handleChoice} />
    ))}
  </DecisionPoints>
  {showFeedback && <ChoiceFeedback />}
  <ScenarioMap showPath={} />
</BranchingScenario>
```

---

## Part 6: Backend Services

### Spaced Repetition Service (SM-2 Algorithm)

**SM-2 Algorithm Implementation**:

```python
from datetime import datetime, timedelta
from typing import Dict

class SpacedRepetitionService:
    """
    Implementation of SuperMemo SM-2 algorithm for spaced repetition.

    Quality ratings:
    5 - Perfect response
    4 - Correct response after hesitation
    3 - Correct response with difficulty
    2 - Incorrect but remembered
    1 - Incorrect but familiar
    0 - Complete blackout
    """

    def calculate_next_review(
        self,
        ease_factor: float,
        interval_days: int,
        repetitions: int,
        quality: int
    ) -> Dict:
        """
        Calculate next review date based on SM-2 algorithm.

        Returns: {
            'ease_factor': float,
            'interval_days': int,
            'repetitions': int,
            'next_review_date': datetime
        }
        """
        # If quality < 3, reset repetitions
        if quality < 3:
            repetitions = 0
            interval_days = 1
        else:
            # Increment repetitions
            repetitions += 1

            # Calculate new interval
            if repetitions == 1:
                interval_days = 1
            elif repetitions == 2:
                interval_days = 6
            else:
                interval_days = int(interval_days * ease_factor)

        # Update ease factor
        ease_factor = ease_factor + (0.1 - (5 - quality) * (0.08 + (5 - quality) * 0.02))

        # Ensure ease factor doesn't go below 1.3
        if ease_factor < 1.3:
            ease_factor = 1.3

        next_review_date = datetime.now() + timedelta(days=interval_days)

        return {
            'ease_factor': round(ease_factor, 2),
            'interval_days': interval_days,
            'repetitions': repetitions,
            'next_review_date': next_review_date
        }

    async def get_due_flashcards(self, user_id: str) -> List:
        """Get all flashcards due for review for a user."""
        # Query database for flashcards where next_review_at <= now
        # Order by next_review_at (oldest first)
        pass

    async def record_review(
        self,
        user_id: str,
        flashcard_id: str,
        quality: int
    ) -> Dict:
        """Record a flashcard review and calculate next review date."""
        # Get current review data
        # Calculate next review using SM-2
        # Update database
        # Return updated data
        pass
```

### AI Service (Claude Integration)

```python
from anthropic import AsyncAnthropic
from typing import AsyncGenerator

class AIService:
    def __init__(self):
        self.client = AsyncAnthropic(api_key=settings.CLAUDE_API_KEY)
        self.system_prompt = self._load_system_prompt()

    def _load_system_prompt(self) -> str:
        """
        Load system prompt that includes:
        - Training content context (119K words)
        - Role definition (helpful aviation tutor)
        - Guidelines for responses
        - Safety emphasis
        """
        return """
        You are an expert powered parachute flight instructor and tutor.
        You have access to comprehensive training materials covering all
        aspects of PPC operation from basic principles to advanced techniques.

        Your role is to:
        - Answer student questions clearly and accurately
        - Provide examples and scenarios
        - Emphasize safety at all times
        - Encourage conservative decision-making
        - Reference specific lessons when relevant

        Training content available:
        [Include embeddings or full text of 119K words]

        Always be encouraging, patient, and thorough. If a student
        asks about something dangerous, emphasize safety first.
        """

    async def chat(
        self,
        user_message: str,
        chat_history: List[Dict],
        current_lesson_context: str = None
    ) -> AsyncGenerator:
        """
        Send message to Claude and stream response.

        Args:
            user_message: User's question
            chat_history: Previous messages in conversation
            current_lesson_context: Optional context from current lesson

        Yields:
            Chunks of AI response for streaming
        """
        messages = chat_history + [
            {"role": "user", "content": user_message}
        ]

        if current_lesson_context:
            # Prepend lesson context to user message
            messages[-1]["content"] = f"""
            Current lesson context: {current_lesson_context}

            Student question: {user_message}
            """

        async with self.client.messages.stream(
            model="claude-3-5-sonnet-20241022",
            max_tokens=2048,
            system=self.system_prompt,
            messages=messages
        ) as stream:
            async for text in stream.text_stream:
                yield text

    async def generate_scenario(
        self,
        topic: str,
        difficulty: str,
        previous_scenarios: List[str] = None
    ) -> Dict:
        """
        Generate a branching decision scenario.

        Returns: {
            'scenario': str,
            'initial_situation': str,
            'decision_points': [
                {
                    'choices': [...],
                    'correct_choice': ...,
                    'feedback': {...}
                }
            ]
        }
        """
        prompt = f"""
        Create a realistic powered parachute flight scenario for training
        purposes on the topic of {topic} at {difficulty} difficulty level.

        The scenario should:
        - Present a realistic situation a pilot might encounter
        - Include 2-3 decision points
        - Provide 3-4 choices at each decision point
        - Include detailed feedback for each choice
        - Emphasize learning points and safety

        Format the response as JSON.
        """

        # Call Claude API
        # Parse response
        # Return structured scenario
        pass

    async def analyze_quiz_performance(
        self,
        user_id: str,
        quiz_attempts: List[Dict]
    ) -> Dict:
        """
        Analyze quiz performance and provide personalized recommendations.

        Returns: {
            'strengths': [...],
            'weaknesses': [...],
            'recommendations': [...],
            'suggested_lessons': [...]
        }
        """
        # Analyze patterns in quiz performance
        # Identify weak areas
        # Use AI to generate personalized recommendations
        pass
```

### Content Import Service

**Import training content from Markdown files**:

```python
import frontmatter
from pathlib import Path
from typing import List, Dict

class ContentImportService:
    """
    Import training content from markdown files into database.
    Preserves structure: modules → lessons
    Generates quizzes from content
    Creates flashcards automatically
    """

    async def import_course_from_directory(
        self,
        directory_path: str,
        course_title: str
    ) -> str:
        """
        Import entire course from directory structure.

        Expected structure:
        training_content/
        ├── 01_foundations/
        │   ├── 01_principles_of_flight.md
        │   └── ...
        ├── 02_regulations/
        │   └── ...

        Returns: course_id
        """
        # Create course
        course = await self.create_course(course_title)

        # Walk directory structure
        base_path = Path(directory_path)
        module_dirs = sorted(base_path.glob("*/"))

        for module_dir in module_dirs:
            # Create module
            module = await self.create_module(
                course.id,
                module_dir.name
            )

            # Import lessons
            lesson_files = sorted(module_dir.glob("*.md"))
            for lesson_file in lesson_files:
                await self.import_lesson(
                    module.id,
                    lesson_file
                )

        return course.id

    async def import_lesson(
        self,
        module_id: str,
        markdown_file: Path
    ):
        """
        Import single lesson from markdown file.

        Markdown file format:
        ---
        title: Lesson Title
        duration: 12
        learning_objectives:
          - Objective 1
          - Objective 2
        ---

        # Lesson Content

        Regular markdown content here...

        ## Section 1
        ...
        """
        # Parse frontmatter and content
        with open(markdown_file, 'r', encoding='utf-8') as f:
            post = frontmatter.load(f)

        # Extract metadata
        title = post.get('title', markdown_file.stem)
        duration = post.get('duration', 10)
        objectives = post.get('learning_objectives', [])

        # Create lesson
        lesson = await db.lessons.create({
            'module_id': module_id,
            'title': title,
            'content': post.content,
            'duration_minutes': duration,
            'learning_objectives': objectives,
            'lesson_type': 'reading'
        })

        # Generate flashcards from content
        await self.generate_flashcards(lesson.id, post.content)

        # Generate quiz questions
        await self.generate_quiz(lesson.id, post.content, objectives)

        return lesson.id

    async def generate_flashcards(
        self,
        lesson_id: str,
        content: str
    ):
        """
        Use AI to generate flashcards from lesson content.

        Identifies:
        - Key terms and definitions
        - Important procedures
        - Critical safety points
        - Facts to memorize
        """
        prompt = f"""
        From the following lesson content, generate 10-15 flashcards
        for spaced repetition study. Focus on:
        - Key terms and definitions
        - Important facts
        - Critical procedures
        - Safety information

        Format as JSON array:
        [
          {{"front": "Question", "back": "Answer", "tags": ["topic"]}},
          ...
        ]

        Content:
        {content[:4000]}  # Truncate if too long
        """

        # Call AI service
        flashcards_json = await ai_service.generate_flashcards(prompt)

        # Insert into database
        for card in flashcards_json:
            await db.flashcards.create({
                'lesson_id': lesson_id,
                'front': card['front'],
                'back': card['back'],
                'tags': card['tags']
            })
```

---

## Part 7: Development Roadmap

### Phase 1: Foundation (Weeks 1-4)

**Week 1: Project Setup**
- [ ] Initialize Git repository
- [ ] Set up Next.js 14 project with TypeScript
- [ ] Set up FastAPI backend with Poetry
- [ ] Configure Docker Compose (PostgreSQL, Redis, app)
- [ ] Set up pre-commit hooks (linting, formatting)
- [ ] Create README with setup instructions

**Week 2: Database & Authentication**
- [ ] Create database schema (all tables)
- [ ] Set up Alembic migrations
- [ ] Implement JWT authentication (FastAPI)
- [ ] Build auth API endpoints
- [ ] Create login/signup UI components
- [ ] Test authentication flow

**Week 3: Core Models & API**
- [ ] Implement Course, Module, Lesson models
- [ ] Create CRUD API endpoints
- [ ] Build basic admin UI for content management
- [ ] Implement file upload to S3/Spaces
- [ ] Test API with Postman/Thunder Client

**Week 4: Content Import**
- [ ] Build content import service
- [ ] Import first module (Principles of Flight)
- [ ] Test content rendering
- [ ] Create lesson viewer component
- [ ] Test on mobile devices

**Deliverable**: Auth working, 1 module imported and viewable

---

### Phase 2: Learning Features (Weeks 5-8)

**Week 5: Quiz System**
- [ ] Implement quiz models and API
- [ ] Build quiz-taking UI component
- [ ] Implement question types (MC, T/F, fill-in-blank)
- [ ] Add immediate feedback
- [ ] Track quiz attempts
- [ ] Test thoroughly

**Week 6: Progress Tracking**
- [ ] Implement progress models
- [ ] Build progress tracking API
- [ ] Create progress dashboard UI
- [ ] Add course enrollment flow
- [ ] Display completion percentages
- [ ] Test progress calculations

**Week 7: Spaced Repetition**
- [ ] Implement SM-2 algorithm
- [ ] Build flashcard models and API
- [ ] Create flashcard review UI
- [ ] Add daily review reminders
- [ ] Test SR algorithm accuracy
- [ ] Generate flashcards for existing lessons

**Week 8: Microlearning Structure**
- [ ] Break all modules into microlearning units
- [ ] Import remaining content
- [ ] Create learning path logic
- [ ] Build course navigation
- [ ] Test complete learning flow

**Deliverable**: Full course imported, quizzes working, SR functional

---

### Phase 3: AI Integration (Weeks 9-12)

**Week 9: AI Chat Tutor**
- [ ] Set up Claude API integration
- [ ] Build chat backend (streaming)
- [ ] Create chat UI component
- [ ] Implement WebSocket for real-time
- [ ] Add conversation history
- [ ] Test with real questions

**Week 10: AI Content Generation**
- [ ] Build scenario generation service
- [ ] Generate practice scenarios
- [ ] Create scenario UI component
- [ ] Test scenario variations
- [ ] Build scenario library

**Week 11: Adaptive Learning**
- [ ] Implement knowledge gap analysis
- [ ] Build recommendation engine
- [ ] Create personalized dashboard
- [ ] Add adaptive quiz difficulty
- [ ] Test personalization accuracy

**Week 12: AI Polish**
- [ ] Improve AI prompt engineering
- [ ] Add context awareness (current lesson)
- [ ] Implement usage limits/quotas
- [ ] Add AI response caching
- [ ] Monitor and optimize costs

**Deliverable**: AI tutor working, scenarios generated, adaptive paths

---

### Phase 4: Gamification & UX (Weeks 13-16)

**Week 13: Gamification System**
- [ ] Implement XP and levels
- [ ] Create achievements/badges
- [ ] Build leaderboard
- [ ] Add study streaks
- [ ] Design reward system
- [ ] Test motivational impact

**Week 14: Interactive Content**
- [ ] Build interactive diagram component
- [ ] Create branching scenario component
- [ ] Add drag-and-drop exercises
- [ ] Implement hotspot interactions
- [ ] Test on mobile

**Week 15: UX Polish**
- [ ] Improve mobile responsiveness
- [ ] Add loading states
- [ ] Implement error handling
- [ ] Create onboarding flow
- [ ] Add tooltips and help
- [ ] Accessibility audit (WCAG AA)

**Week 16: Testing & Bug Fixes**
- [ ] Comprehensive testing (all features)
- [ ] Fix critical bugs
- [ ] Performance optimization
- [ ] Cross-browser testing
- [ ] User acceptance testing
- [ ] Address feedback

**Deliverable**: Polished, gamified, accessible platform

---

### Phase 5: Launch Preparation (Weeks 17-20)

**Week 17: Production Setup**
- [ ] Set up production hosting (Railway/Render/DO)
- [ ] Configure CI/CD pipeline
- [ ] Set up monitoring (Sentry)
- [ ] Configure backups
- [ ] SSL/security audit
- [ ] Load testing

**Week 18: Content Final Review**
- [ ] Review all lesson content
- [ ] Test all quizzes
- [ ] Verify flashcards
- [ ] Check for errors/typos
- [ ] Ensure consistent formatting
- [ ] Add missing media

**Week 19: Documentation & Marketing**
- [ ] Write user guide
- [ ] Create video tutorials
- [ ] Build landing page
- [ ] Set up analytics
- [ ] Prepare launch announcement
- [ ] Create social media content

**Week 20: Beta Launch**
- [ ] Invite 10-20 beta testers
- [ ] Monitor usage closely
- [ ] Gather feedback
- [ ] Fix urgent issues
- [ ] Iterate based on data
- [ ] Prepare for public launch

**Deliverable**: Production-ready platform with beta users

---

## Part 8: Cost Estimation

### Development Costs

**DIY Development (Solo, 20-30 hrs/week)**:
- **Time investment**: 300-500 hours over 20 weeks
- **Opportunity cost**: $0 (your time)
- **Actual cost**: $0
- **Best if**: You're a developer or want to learn

**Hired Development (Freelancer)**:
- **Rate**: $50-150/hour (depending on region/experience)
- **Hours**: 400-600 hours
- **Total**: $20,000-90,000
- **Best if**: You have budget, want fast delivery

**Team Development (Agency)**:
- **Cost**: $50,000-150,000+
- **Timeline**: 3-6 months
- **Best if**: Large budget, enterprise needs

### Infrastructure Costs (Annual)

**Option A: Railway.app (Recommended for MVP)**:
- Hobby plan: $5/month → $60/year
- Pro plan (when you scale): $20/month → $240/year
- Database: Included
- Redis: Included
- Total Year 1: ~$100-300

**Option B: DigitalOcean**:
- App Platform (2 apps @ $12 each): $288/year
- Managed PostgreSQL ($15/mo): $180/year
- Managed Redis ($15/mo): $180/year
- Spaces (storage): $60/year
- Total Year 1: ~$700/year

**Option C: Self-Hosted VPS**:
- 8GB RAM Droplet: $48/month → $576/year
- Spaces: $60/year
- Backups: $60/year
- Total Year 1: ~$700/year

### Third-Party Services (Annual)

**Required**:
- Domain name: $15/year
- Claude API: $100-1,000/year (depends on usage)
- Email service (SendGrid/Resend): $0-200/year
- **Subtotal**: $115-1,215/year

**Optional**:
- Error tracking (Sentry): $0-26/month → $0-312/year
- Analytics (Plausible): $108/year
- Uptime monitoring (UptimeRobot): $0-60/year
- **Subtotal**: $0-480/year

### Total Cost Summary

**Year 1 (DIY Development)**:
- Development: $0 (your time)
- Infrastructure: $100-700
- Services: $115-1,695
- **Total: $215-2,395**

**Year 2+ (Ongoing)**:
- Development: Maintenance only (minimal)
- Infrastructure: $100-700
- Services: $115-1,695
- **Total: $215-2,395/year**

**Year 1 (Hired Development)**:
- Development: $20,000-90,000
- Infrastructure: $100-700
- Services: $115-1,695
- **Total: $20,215-92,395**

---

## Part 9: Getting Started - Next Steps

### Immediate Action Plan (This Week)

**Day 1: Decision & Planning**
- [ ] Decide: DIY or hire help?
- [ ] If DIY: Assess your skills (React? Python? Both?)
- [ ] If hiring: Start interviewer process
- [ ] Review this spec document thoroughly
- [ ] Identify questions or concerns

**Day 2-3: Environment Setup**
- [ ] Install development tools:
  - Node.js 18+ and npm/yarn
  - Python 3.11+
  - Docker Desktop
  - VSCode (or preferred IDE)
  - PostgreSQL client (TablePlus, pgAdmin)
- [ ] Set up accounts:
  - GitHub (for code)
  - Claude API (Anthropic)
  - Railway.app or chosen host
  - Domain registrar

**Day 4-5: Project Initialization**
- [ ] Create GitHub repository
- [ ] Initialize Next.js project
- [ ] Initialize FastAPI project
- [ ] Set up Docker Compose
- [ ] Create initial database schema
- [ ] Verify local environment works

**Day 6-7: First Feature**
- [ ] Build simple auth (register/login)
- [ ] Create first API endpoint
- [ ] Display "Hello World" on frontend
- [ ] Connect frontend to backend
- [ ] Celebrate first milestone! 🎉

### Learning Resources

**If you're learning as you build**:

**Next.js/React**:
- Next.js official tutorial: nextjs.org/learn
- React docs: react.dev
- YouTube: "Next.js 14 Full Course" by Traversy Media

**FastAPI/Python**:
- FastAPI official tutorial: fastapi.tiangolo.com/tutorial
- "FastAPI Full Course" on YouTube
- Real Python tutorials

**PostgreSQL**:
- PostgreSQL tutorial: postgresqltutorial.com
- SQLAlchemy docs: docs.sqlalchemy.org

**Docker**:
- Docker Getting Started guide
- "Docker Tutorial for Beginners" on YouTube

### Community & Support

**Where to get help**:
- FastAPI Discord: discord.gg/fastapi
- Next.js Discord: discord.com/invite/nextjs
- Stack Overflow: Tag questions appropriately
- Reddit: r/FastAPI, r/nextjs, r/learnprogramming
- AI pair programming: Use Claude or ChatGPT to debug

---

## Conclusion

You now have a complete, detailed specification for building a custom, open-source powered parachute training platform. This platform will:

✅ Transform your 119,000-word training content into engaging microlearning
✅ Implement evidence-based learning techniques (SR, active recall, microlearning)
✅ Integrate AI for personalized tutoring and adaptive learning
✅ Provide gamification for motivation and engagement
✅ Track detailed progress and analytics
✅ Scale from MVP to thousands of students
✅ Cost $200-2,400/year to operate (after development)
✅ Give you 100% ownership and control

**The path is clear. The tools are ready. The content is prepared.**

**What do you want to tackle first?**

1. Set up development environment
2. Design the database schema in detail
3. Build the first API endpoint
4. Create the lesson viewer component
5. Import first module content
6. Something else?

Let me know, and I'll help you get started!

---

**Document Version**: 1.0
**Created**: November 8, 2025
**Status**: Ready for Implementation
**Next**: Begin Phase 1, Week 1
