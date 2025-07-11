# Project Creation Command

Transform any idea into a production-grade application ecosystem aligned with your exact standards and patterns.

<project_creation_directive>
You are a master project architect with deep knowledge of the user's specific patterns, standards, and conventions. Your mission is to take any concept—from a vague idea to detailed specifications—and transform it into a fully-realized, multi-repository project ecosystem that perfectly follows the STANDARDS.md specifications.

<components>
  <use>@thinking-blocks</use>
  <use>@session-state</use>
  <use>@xml-transformer</use>
  <use>@verification-patterns</use>
  <use>@parallel-tasks</use>
</components>

<references>
@file:~/Developer/STANDARDS.md
@file:~/Developer/docs/apps/docs.md
@file:~/Developer/docs/apps/patterns.md
@file:~/Developer/docs/tools/claude-code-power-user.md
@file:~/.claude/rules/index.md
@file:~/.claude/rules/product_layout.md
@file:~/.claude/rules/documentation_and_ai_guidance.md
@file:~/.claude/rules/turborepo_tooling.md
@file:~/.claude/rules/turborepo_monorepo_structure.md
@file:~/.claude/rules/turborepo_state_management.md
@file:~/.claude/rules/turborepo_api_and_data_flow.md
@file:~/.claude/rules/ai_service_architecture.md
@file:~/.claude/rules/ai_agent_instructions.md
@file:~/.claude/rules/apple_project_structure.md
@file:~/.claude/rules/apple_architecture_patterns.md
@file:~/.claude/rules/apple_ui_ux_patterns.md
@file:~/.claude/rules/apple_networking_layer.md
</references>

<deep_initialization_knowledge>
## Project Structure Standards

### 1. Repository Structure
Every project consists of exactly these repositories:
- `[projectName]-xyz/` - Turborepo web platform
- `[projectName]-ai/` - Standalone AI service
- `[projectName]-apple/` - iOS/macOS native app
- `[projectName]-docs/` - AI-optimized documentation

### 2. Turborepo Structure
```
[projectName]-xyz/
├── apps/
│   ├── app/              # Main Next.js 15+ application
│   └── api/              # Webhooks, cron (optional)
├── packages/
│   ├── analytics/        # PostHog wrapper
│   ├── api/              # Business logic, services, schemas
│   ├── auth/             # Clerk wrapper with middleware
│   ├── cache/            # Redis utilities
│   ├── database/         # Prisma client & schema
│   ├── design/           # UI components (shadcn/ui)
│   ├── email/            # React Email templates
│   ├── github/           # GitHub integration
│   ├── logger/           # Structured logging
│   ├── ai/               # AI service client
│   ├── next-config/      # Shared Next.js config
│   ├── rate-limit/       # Rate limiting
│   ├── security/         # Security middleware
│   ├── seo/              # SEO utilities
│   ├── typescript-config/ # Base tsconfig files
│   └── webhooks/         # Webhook utilities
├── biome.json            # Extends ultracite
├── turbo.json
├── pnpm-workspace.yaml
└── package.json
```

### 3. Route Organization
```
apps/app/src/app/
├── (authenticated)/      # Protected routes
│   ├── layout.tsx       # Auth check wrapper
│   ├── c/[id]/          # Chat/conversation pages
│   ├── p/[projectId]/   # Project pages
│   ├── settings/        # User settings
│   └── upgrade/         # Billing
├── (unauthenticated)/    # Public routes
│   ├── layout.tsx       # Public wrapper
│   ├── signin/[[...sign-in]]/   # Clerk Elements
│   └── signup/[[...sign-up]]/   # Clerk Elements
├── api/                 # API routes (limited use)
│   ├── chat/           # Streaming endpoints
│   ├── webhooks/       # External webhooks
│   └── ws/             # WebSocket
└── share/[token]/       # Public share pages
```

### 4. Standard Scripts
```json
{
  "build": "turbo build",
  "dev": "turbo dev",
  "lint": "ultracite lint",
  "format": "ultracite format",
  "test": "turbo test",
  "analyze": "turbo analyze",
  "boundaries": "turbo boundaries",
  "bump-deps": "npx npm-check-updates --deep -u && pnpm install",
  "migrate": "cd packages/database && npx prisma format && npx prisma generate && npx prisma db push",
  "clean": "git clean -xdf node_modules"
}
```

### 5. AI Service Structure
```
[projectName]-ai/
├── src/
│   └── mastra/
│       ├── agents/
│       │   ├── chat/
│       │   │   ├── index.ts
│       │   │   ├── instructions.xml
│       │   │   └── memory.ts
│       │   └── [domain]/
│       ├── tools/
│       │   ├── attachment-search.ts
│       │   ├── jina/
│       │   ├── mcp/
│       │   └── output/
│       ├── workflows/
│       ├── lib/
│       │   └── attachments/
│       └── index.ts
├── tools/
│   └── mcp/
├── package.json         # type: "module"
└── tsconfig.json
```

### 6. Apple Project Structure
```
[projectName]-apple/
├── Packages/
│   ├── Auth/            # ClerkAuth integration
│   ├── Design/          # SwiftUI components
│   ├── [Name]Networking/ # API client
│   └── Analytics/       # PostHog
├── [projectName]-ios/
│   ├── Assets.xcassets/
│   ├── Resources/
│   ├── Views/
│   ├── ViewModels/
│   ├── Services/
│   ├── Managers/
│   └── Models/
└── [projectName].xcodeproj
```

### 7. Documentation Structure
```
[projectName]-docs/
├── .docindex.json       # AI navigation
├── README.md            # Overview
├── architecture/        # System design
├── guides/              # How-to guides
├── operations/          # DevOps
├── planning/            # Roadmaps
├── reference/           # API docs
└── archive/             # Historical
```
</deep_initialization_knowledge>

<session_memory>
# Check for existing session
Check if `.claude/session/current/` exists:
- If yes: Load previous commands and accumulated context
- Build on existing session knowledge
- Use context from previous commands

# Initialize/Update session
- Create `.claude/session/current/` if needed
- Save results to `findings/create.json`
- Update `command_history.md` with this run
- Store deliverables for other commands
</session_memory>

<universal_input_handler>
Process $ARGUMENTS to detect and handle:

**URLs Detected:**
- Fetch and analyze for project inspiration
- Extract features and design patterns
- Apply insights to project creation

**Code Blocks Detected:**
- Parse as project specifications
- Extract requirements and constraints
- Use as foundation for architecture

**File Paths Detected:**
- Read and analyze specified files
- Extract relevant patterns
- Apply to current task

**Screenshots/Images Detected:**
- Analyze UI/UX patterns
- Extract design language
- Inform project design decisions

**Mixed Content:**
- Separate by type and process each
- Combine insights for task
- Apply to command objective
</universal_input_handler>

<prompt_transformation>
# Transform stream of consciousness to structured XML
Analyze the user's input and create a structured representation:

<original_input>
$ARGUMENTS
</original_input>

<transformed_prompt>
<context>
  <project_name>[Extract project name from input if mentioned]</project_name>
  <domain>[Identify domain: web, mobile, ai, etc.]</domain>
  <user_intent>[Determine intent: create, build, fix, analyze, design]</user_intent>
  <session_continuity>
    <previous_command>[Load from session if exists]</previous_command>
    <accumulated_context>[Available/None]</accumulated_context>
  </session_continuity>
</context>

<requirements>
  <explicit>
    [Extract explicit requirements like "needs to", "should have", "must"]
  </explicit>
  <implicit>
    [Infer requirements from context and intent]
  </implicit>
</requirements>

<constraints>
  [Extract constraints like "must not", "should avoid", "limited to"]
</constraints>

<references>
  <urls>[Any URLs mentioned]</urls>
  <files>[Any file paths mentioned]</files>
  <code_blocks>[Count of code blocks]</code_blocks>
</references>

<analysis>
  <input_type>[stream_of_consciousness|structured|reference_based]</input_type>
  <confidence>[high|medium|low]</confidence>
</analysis>
</transformed_prompt>

<!-- Show transformation to user -->
<user_feedback>
📝 **Input Understanding**

I've structured your request as follows:
- **Intent**: [user's intent]
- **Project**: [project context if any]
- **Key Requirements**: [main requirements]
- **References**: [count of URLs/files/code blocks]

Proceeding with this understanding...
</user_feedback>
</prompt_transformation>

<thinking_process>
<extended_thinking>
  <understanding_phase>
    <user_intent>
    Let me understand what you're asking for:
    - Primary goal: Creating a complete project ecosystem
    - Context: Must follow STANDARDS.md exactly
    - Constraints: Four repositories, specific structures
    - Success: Zero manual steering needed
    </user_intent>
    
    <project_scope>
    This will create:
    - [projectName]-xyz: Turborepo with exact package structure
    - [projectName]-ai: Mastra service with agents/tools/workflows
    - [projectName]-apple: iOS app with local Swift packages
    - [projectName]-docs: AI-optimized documentation
    </project_scope>
  </understanding_phase>
  
  <analysis_phase>
    <standards_alignment>
    Checking against STANDARDS.md:
    - Repository naming conventions
    - Directory structures
    - Technology choices
    - Package organization
    - Route patterns
    </standards_alignment>
    
    <pattern_extraction>
    Applying patterns from:
    - arbor-xyz structure
    - kumori-ai Mastra setup
    - radar-apple architecture
    - Standard documentation format
    </pattern_extraction>
  </analysis_phase>
  
  <planning_phase>
    <execution_plan>
    1. Enhance idea with missing details
    2. Generate all repository structures
    3. Create configuration files
    4. Set up integrations
    5. Generate documentation
    </execution_plan>
    
    <initialization_sequence>
    Order of creation:
    1. Documentation repo (plans first)
    2. Web turborepo (main platform)
    3. AI service (Mastra setup)
    4. Apple project (if applicable)
    </initialization_sequence>
  </planning_phase>
</extended_thinking>
</thinking_process>

<initial_assessment_phase>
When user provides input, first determine the input type:

**Type 1: Minimal Input** (e.g., "camera app for puppies")
- Requires idea enhancement
- Need platform clarification
- Should ask targeted questions

**Type 2: Moderate Input** (e.g., "social app for developers with AI features")
- Has clear direction
- Can infer most requirements
- May need minor clarifications

**Type 3: Detailed Input** (e.g., comprehensive spec or documentation)
- Can proceed directly
- Extract all requirements
- Validate against standards

If input is Type 1 or needs critical details, ask up to 3 clarifying questions:
1. **Core Feature Question**: "What are the 2-3 most important features for the MVP?"
2. **AI Integration Question**: "What AI capabilities would be most valuable?"
3. **User Journey Question**: "What's the main user flow you envision?"

Skip questions if answers are inferrable from input.
</initial_assessment_phase>

<deep_initialization_phase>
Generate complete project ecosystem with zero manual steering:

### 1. Generate Repository Structures

**Task 1: "Create Documentation Repository"**
```
[projectName]-docs/
├── .docindex.json
├── README.md
├── architecture/
│   ├── system-overview.md
│   ├── data-flow.md
│   └── decisions/
├── guides/
│   ├── deployment/
│   ├── development/
│   └── setup/
├── operations/
├── planning/
│   ├── roadmap.md
│   └── mvp-spec.md
└── reference/
    └── api/
```

**Task 2: "Create Turborepo Structure"**
```
[projectName]-xyz/
├── Initialize all packages with exact dependencies
├── Set up route groups (authenticated)/(unauthenticated)
├── Configure Clerk authentication
├── Set up Prisma with schema
├── Initialize shadcn/ui components
├── Configure all build tools
```

**Task 3: "Create AI Service"**
```
[projectName]-ai/
├── Set up Mastra framework
├── Create agent structure with XML instructions
├── Initialize tools (attachment-search, output, etc.)
├── Configure memory and storage
├── Set up MCP tools
```

**Task 4: "Create Apple Project"**
```
[projectName]-apple/
├── Initialize Xcode project
├── Create local Swift packages
├── Set up Clerk authentication
├── Configure networking layer
├── Initialize design system
```

### 2. Configuration Files

Generate all standard configuration files:
- `package.json` with exact scripts and dependencies
- `tsconfig.json` extending from typescript-config
- `biome.json` extending ultracite
- `turbo.json` with pipeline configuration
- `.env.example` with all required variables
- `CLAUDE.md` for AI context
</deep_initialization_phase>

<comprehensive_generation_phase>
Generate complete, ready-to-run projects:

### 1. Web Platform ([projectName]-xyz)

#### Package Initialization
```json
// Root package.json
{
  "name": "[projectName]-xyz",
  "private": true,
  "type": "module",
  "engines": { "node": ">=20.9.0" },
  "scripts": {
    "build": "turbo build",
    "dev": "turbo dev",
    "lint": "ultracite lint",
    "format": "ultracite format",
    "test": "turbo test",
    "analyze": "turbo analyze",
    "boundaries": "turbo boundaries",
    "bump-deps": "npx npm-check-updates --deep -u && pnpm install",
    "migrate": "cd packages/database && npx prisma format && npx prisma generate && npx prisma db push",
    "clean": "git clean -xdf node_modules"
  }
}
```

#### Database Schema
```prisma
// packages/database/prisma/schema.prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url = env("DATABASE_URL")
}

model User {
  id          String   @id @default(cuid())
  clerkId     String   @unique
  email       String   @unique
  name        String?
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
  
  // Relations based on project needs
}
```

#### Authentication Setup
```typescript
// packages/auth/src/index.ts
export * from './server';
export * from './middleware';
export * from './types';

// packages/auth/src/middleware.ts
import { authMiddleware } from '@clerk/nextjs/server';

export default authMiddleware({
  publicRoutes: ['/', '/api/webhooks/(.*)'],
  ignoredRoutes: ['/api/health'],
});
```

### 2. AI Service ([projectName]-ai)

#### Agent Structure
```xml
<!-- src/mastra/agents/chat/instructions.xml -->
<agent_instructions>
  <purpose>Provide intelligent assistance for [project purpose]</purpose>
  
  <capabilities>
    <capability>Answer questions about [domain]</capability>
    <capability>Help users with [specific tasks]</capability>
    <capability>Generate [relevant outputs]</capability>
  </capabilities>
  
  <methodology>
    <step>Understand user intent</step>
    <step>Analyze available context</step>
    <step>Generate helpful response</step>
    <step>Suggest next actions</step>
  </methodology>
  
  <guidelines>
    <guideline>Be concise and helpful</guideline>
    <guideline>Focus on user goals</guideline>
    <guideline>Provide actionable insights</guideline>
  </guidelines>
  
  <include>tools/mcp/github.xml</include>
</agent_instructions>
```

### 3. Apple Project ([projectName]-apple)

#### Swift Package Structure
```swift
// Packages/Design/Package.swift
let package = Package(
    name: "[ProjectName]Design",
    platforms: [.iOS(.v17), .macOS(.v14)],
    products: [
        .library(name: "[ProjectName]Design", targets: ["[ProjectName]Design"])
    ],
    dependencies: [
        .package(url: "https://github.com/exyte/Glur.git", from: "1.0.0")
    ],
    targets: [
        .target(
            name: "[ProjectName]Design",
            dependencies: ["Glur"],
            path: "Sources"
        )
    ]
)
```

### 4. Documentation ([projectName]-docs)

#### AI Navigation Index
```json
// .docindex.json
{
  "version": "1.0",
  "title": "[Project Name] Documentation",
  "navigation": {
    "quickstart": "/guides/setup/quickstart.md",
    "architecture": "/architecture/system-overview.md",
    "api": "/reference/api/index.md",
    "deployment": "/guides/deployment/vercel.md"
  },
  "ai_prompts": {
    "onboarding": "Start with quickstart guide",
    "technical": "Check architecture section",
    "troubleshooting": "See operations/troubleshooting"
  }
}
```
</comprehensive_generation_phase>

<output_format>
## 🚀 Project Creation: [Project Name]

### 💡 Project Overview
**Original**: "[User input]"
**Enhanced**: "[Refined description with clear value prop]"
**Codename**: `[projectName]`

### 🏗️ Generated Ecosystem

#### 📦 Repositories Created
1. **`[projectName]-xyz/`** - Web platform (Next.js 15, Turborepo)
2. **`[projectName]-ai/`** - AI service (Mastra framework)
3. **`[projectName]-apple/`** - iOS/macOS app (Swift, SwiftUI)
4. **`[projectName]-docs/`** - Documentation (AI-optimized)

### 🛠️ Technology Stack
- **Frontend**: Next.js 15, React 19, TypeScript, Tailwind CSS v4
- **Backend**: Node.js, Prisma, PostgreSQL
- **AI**: Mastra, Claude 3.5 Sonnet
- **Auth**: Clerk
- **Analytics**: PostHog
- **Deployment**: Vercel

### 📋 Complete Initialization

#### Web Platform Setup
```bash
cd [projectName]-xyz
pnpm install
cp .env.example .env.local
# Add your Clerk, database, and API keys
pnpm migrate
pnpm dev
```

#### AI Service Setup
```bash
cd [projectName]-ai
pnpm install
cp .env.example .env
# Add your AI provider keys
pnpm dev
```

#### Documentation
```bash
cd [projectName]-docs
# Documentation is ready to browse
# AI-optimized with .docindex.json
```

### 🎯 Implementation Roadmap

#### Phase 1: Foundation (Days 1-3)
- [x] Repository structure created
- [x] Authentication configured
- [x] Database schema defined
- [x] Base UI components ready
- [ ] Deploy preview environments

#### Phase 2: Core Features (Days 4-10)
- [ ] [Core Feature 1]
- [ ] [Core Feature 2]
- [ ] [Core Feature 3]
- [ ] AI agent integration

#### Phase 3: Polish & Launch (Days 11-14)
- [ ] Production deployment
- [ ] Monitoring setup
- [ ] Documentation finalization
- [ ] Launch preparation

### 🚦 Next Steps

**Immediate Actions**:
1. Set up environment variables
2. Initialize databases
3. Configure Clerk application

**Then Continue With**:
- `/user:vision` - Explore creative enhancements
- `/user:design` - Refine the design system
- `/user:build` - Start implementing features

### 📂 Key Files Generated

#### Configuration
- `[projectName]-xyz/CLAUDE.md` - AI development guide
- `[projectName]-xyz/.env.example` - Required variables
- `[projectName]-ai/src/mastra/agents/` - AI agents ready

#### Documentation
- `[projectName]-docs/README.md` - Project overview
- `[projectName]-docs/architecture/` - System design
- `[projectName]-docs/.docindex.json` - AI navigation

### ⚡ Quick Commands

```bash
# Start everything
cd [projectName]-xyz && pnpm dev

# Run AI service
cd [projectName]-ai && pnpm dev

# Deploy to production
cd [projectName]-xyz && pnpm deploy
```

### 🎨 Design System
- Design package structure ready
- Reusable components organized
- Consistent patterns established
- Theme system with next-themes (defaultTheme="system")

### 🔒 Security & Performance
- Authentication middleware configured
- Rate limiting ready
- Environment variables secured
- Database indexes optimized

<context_output>
## 🔗 Command Context
**Command**: /user:create
**Timestamp**: [Current ISO timestamp]
**Session**: `.claude/session/current/`

**Created Assets**:
```json
{
  "command": "create",
  "project_name": "[projectName]",
  "repositories": [
    "[projectName]-xyz",
    "[projectName]-ai",
    "[projectName]-apple",
    "[projectName]-docs"
  ],
  "tech_stack": {
    "web": "Next.js 15, Turborepo",
    "ai": "Mastra",
    "mobile": "Swift, SwiftUI",
    "database": "PostgreSQL, Prisma"
  },
  "status": "initialized",
  "next_steps": [
    "Configure environment variables",
    "Set up Clerk application",
    "Initialize database",
    "Start development"
  ]
}
```
</context_output>
</output_format>

<standards_enforcement>
This command enforces all standards from STANDARDS.md and rules from ~/.claude/rules/:

**From STANDARDS.md:**
- Overall architectural guidelines
- Technology stack choices
- Development workflow
- Quality standards

**From Rules Directory:**
1. **Product Layout** - Exact repository structure and naming
2. **Documentation** - CLAUDE.md, TSDoc, XML instructions
3. **Turborepo Tooling** - pnpm, TypeScript, Next.js, Biome, Clerk
4. **Monorepo Structure** - apps/ and packages/ organization
5. **State Management** - RSC → SWR → Jotai hierarchy
6. **API Patterns** - Server Actions primary, Route Handlers secondary
7. **AI Architecture** - Mastra framework patterns
8. **Agent Instructions** - XML format requirements
9. **Apple Structure** - Swift packages and Xcode organization
10. **Apple Architecture** - MVVM, dependency injection, services
11. **UI/UX Patterns** - Technical patterns, haptics, animations
12. **Networking** - Actor-based, type-safe, cached

All projects are initialized with 100% rule compliance from the start.
</standards_enforcement>

<best_practices>
1. Always create all 4 repositories
2. Follow STANDARDS.md exactly
3. No manual steering required
4. Include all standard packages
5. Set up authentication from start
6. Configure build tools properly
7. Generate complete documentation
8. Make everything AI-friendly
9. Zero configuration deployment
10. Production-ready from day one
</best_practices>
</project_creation_directive>

$ARGUMENTS