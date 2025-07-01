# Multi-Agent Planning Command

Create a comprehensive, agent-scoped implementation plan for the specified goal.

<planning_directive>
You are tasked with creating a fully formed plan that divides a complex goal into independent, agent-scoped implementation tasks. Each agent should be able to work autonomously with clear boundaries and interfaces.

<requirements>
- Create a thorough planning document structure in a dedicated directory (e.g., docs/implementation/[project-name]/)
- Write detailed agent-scoped planning documents for each independent task
- Each agent document must be self-contained with clear scope, dependencies, and deliverables
- Use context7 liberally to research external dependencies and best practices
- Include implementation examples, code snippets, and architectural patterns
- Provide effort estimates and success metrics for each agent
- Create a README.md that coordinates all agents and shows the integration flow
</requirements>

<research_approach>
Before creating the plan:
1. Fully read through all relevant source files and directories
2. Use context7 to deeply understand external dependencies and technologies
3. Analyze existing architecture and integration points
4. Consider creative approaches and additional value-add features
</research_approach>

<goal>
$ARGUMENTS
</goal>

<output_structure>
Create the following documentation structure:
1. **Overview document** - High-level integration plan and architecture
2. **Agent-specific documents** - One per independent implementation task:
   - Agent scope and packages to modify
   - Detailed implementation plan with code examples
   - Dependencies on other agents
   - Testing strategy
   - Security considerations
   - Effort estimate (in developer days)
   - Success metrics
3. **README.md** - Coordination document with:
   - Architecture diagram (ASCII or description)
   - Implementation timeline
   - Agent dependencies matrix
   - Total effort estimate

Each agent should focus on a specific aspect (e.g., infrastructure, API integration, UI/UX, core functionality, etc.) and be implementable by an independent developer.
</output_structure>

<planning_principles>
- Break complex systems into manageable, independent components
- Define clear interfaces between agents/components
- Prioritize completeness - each agent document should answer all questions a developer might have
- Include both immediate implementation and future enhancement possibilities
- Consider security, performance, and scalability in each component
- Provide concrete code examples and patterns, not just high-level descriptions
</planning_principles>

<example_agent_structure>
# Agent [Number]: [Descriptive Name]
*"[One-line mission statement]"*

## Scope
[Clear description of what this agent will accomplish]

## Packages to modify
- `apps/[app-name]` - [what will be modified]
- `packages/[package-name]` - [what will be modified]

## Implementation Details
[Detailed technical implementation with code examples]

## Dependencies
- Agent [X] must complete [specific deliverable] first
- Requires [external service/tool] to be configured

## Testing Strategy
[How to verify this agent's work is complete and correct]

## Security Considerations
[Any security implications or requirements]

## Effort Estimate
[X-Y developer days]

## Success Metrics
- [ ] [Specific measurable outcome]
- [ ] [Another measurable outcome]
</example_agent_structure>
</planning_directive>

Begin by acknowledging the goal, then proceed with thorough research using all available tools before creating the comprehensive plan.
