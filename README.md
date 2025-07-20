<div align="center">
  <img src="https://v3.fal.media/files/tiger/zgBf7InmAUs1OrMLbBAqQ.png" alt="claude-commands logo" width="80" height="80">
  
  # claude-commands
  
  **specialized command system for claude code with ai-driven workflows**
</div>

<br>

## Overview

Claude Code commands provide specialized, structured workflows that transform natural language requests into executable development tasks. Each command integrates seamlessly with others through shared context and standardized patterns.

## Command Directory

The system includes specialized commands for different development phases:

- **`prime.md`** - Session context initialization
- **`create.md`** - Project creation and planning
- **`build.md`** - Implementation execution  
- **`vision.md`** - Creative exploration and ideation
- **`design.md`** - Design system creation
- **`brand.md`** - Production readiness and polish
- **`docs.md`** - Documentation generation
- **`audit.md`** - Code and documentation review
- **`diagram.md`** - Visual architecture creation

## Architecture

Each command follows a standardized structure:

1. **Universal Input Handler** - Processes URLs, code, files, images
2. **XML Transformer** - Converts natural language to structured format
3. **Thinking Blocks** - Shows reasoning process transparently
4. **Verification Patterns** - Ensures safe execution
5. **Session State** - Maintains context across commands
6. **Output Standards** - Consistent formatting

## Component System

Reusable components in `/components/`:
- `thinking-blocks.md` - Structured reasoning patterns
- `xml-transformer.md` - Input transformation logic
- `verification-patterns.md` - Safety checks
- `session-state.md` - Context management
- `planning-phases.md` - Planning methodologies
- `output-standards.md` - Output formatting
- `interop-patterns.md` - Command integration

## Progressive Enhancement

Commands build on each other's outputs:
```
prime → vision → create → build → audit
```

Each stage enhances the context and capabilities available to subsequent commands.

## Session Management

The system maintains persistent state:
- Context accumulation across commands
- Automatic session archival
- Smart context selection
- Cross-command data flow

## Development Standards

All commands follow:
- Component-based architecture
- Session-aware execution
- Standardized verification
- Consistent output formatting
- Transparent reasoning display

## Usage

Commands integrate naturally with Claude Code workflows, providing structured approaches to complex development tasks while maintaining flexibility and transparency.

---

*Built for Claude Code - enhancing AI development workflows through structured commands*