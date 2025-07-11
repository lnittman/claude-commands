# Rule: Product Layout

## 1. Monorepo and Standalone Services
A product must be organized into a primary web monorepo (`*-xyz`) and one or more standalone service directories. This isolates platform-specific concerns. The standard layout is:

-   `[product-name]-xyz/`: The web platform, managed as a Turborepo monorepo with PNPM.
-   `[product-name]-ai/`: The AI service, managed as a standalone Node.js/TypeScript project. It must not be part of the web monorepo's workspace.
-   `[product-name]-apple/`: The native Apple platform project (if applicable).
-   `[product-name]-docs/`: Centralized documentation for the entire product.

## 2. Web Monorepo (`-xyz`) Structure
The web monorepo must contain two primary directories: `apps` and `packages`.

-   `apps/`: Contains deployable applications.
    -   `app/`: The main Next.js user-facing application.
    -   `api/`: Optional, for services like webhooks or cron jobs that are deployed separately.
-   `packages/`: Contains shared code and libraries.
    -   `api/`: Shared business logic, domain services, and Zod schemas.
    -   `auth/`: Authentication logic, primarily as a wrapper for Clerk.
    -   `database/`: The Prisma client, schema, and migrations.
    -   `design/`: The shared UI component library, hooks, and constants.
    -   `ai/`: The generalized AI client SDK for the web application.
    -   `typescript-config/`: Shared `tsconfig.json` files.

## 3. AI Service (`-ai`) Structure
The AI service must be a standalone project dedicated to defining and running all AI logic.

-   `src/mastra/`: The root for all AI definitions.
    -   `agents/`: Contains definitions for each AI agent (e.g., `chat`, `code`).
    -   `tools/`: Contains definitions for tools that agents can use.
    -   `workflows/`: Defines multi-step processes that combine agents and tools.
    -   `lib/`: Contains shared utilities, such as the RAG implementation for attachments.