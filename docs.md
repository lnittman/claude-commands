# Documentation Command

Perform comprehensive documentation operations including audits, creation, enhancement, and maintenance of the [projectName]-docs repository.

<documentation_audit_directive>
You are tasked with conducting a thorough audit of a codebase's documentation state and creating a comprehensive plan to establish or enhance a dedicated documentation repository that follows industry best practices and is optimized for AI-assisted development.

<components>
  <use>@thinking-blocks</use>
  <use>@session-state</use>
  <use>@xml-transformer</use>
  <use>@verification-patterns</use>
</components>

<reference>
@file:~/Developer/docs/apps/docs.md
</reference>

<session_memory>
# Check for existing session
Check if `.claude/session/current/` exists:
- If yes: Load previous commands and accumulated context
- Build on existing session knowledge
- Use context from previous commands

# Initialize/Update session
- Create `.claude/session/current/` if needed
- Save results to `findings/docs.json`
- Update `command_history.md` with this run
- Store deliverables for other commands
</session_memory>

<universal_input_handler>
Process $ARGUMENTS to detect and handle:

**URLs Detected:**
- Fetch and analyze documentation examples
- Extract documentation patterns
- Apply best practices to audit

**Code Blocks Detected:**
- Parse as documentation examples
- Extract structure and patterns
- Apply to documentation plan

**File Paths Detected:**
- Read and analyze specified files
- Extract relevant patterns
- Apply to current task

**Screenshots/Images Detected:**
- Analyze documentation layouts
- Extract visual hierarchy
- Inform documentation design

**Mixed Content:**
- Separate by type and process each
- Combine insights for task
- Apply to command objective
</universal_input_handler>

<prompt_transformation>
<!-- Use enhanced XML transformer component -->
<input_analysis>
  <raw_input>$ARGUMENTS</raw_input>
  <detect_documentation_intent>
    - Documentation audit request
    - Coverage assessment
    - Quality improvement
    - New documentation creation
    - Migration planning
  </detect_documentation_intent>
</input_analysis>

<semantic_extraction>
  <documentation_context>
    - Is this for existing or new project?
    - Specific documentation types mentioned?
    - Quality concerns highlighted?
    - Compliance requirements?
  </documentation_context>
  
  <documentation_scope>
    - API documentation needs
    - Architecture documentation
    - User guides and tutorials
    - Developer onboarding
    - Operations and deployment
  </documentation_scope>
</semantic_extraction>

<transformation_feedback>
## 🔄 Understanding Your Documentation Audit Request

**Interpreted as**: {{documentation_interpretation}}

**Audit focus**: {{primary_documentation_concern}}

**Key elements identified**:
{{#if project_path}}- 📁 Project: {{project_path}}{{/if}}
{{#if existing_docs}}- 📄 Existing documentation found{{/if}}
{{#if coverage_request}}- 📊 Coverage analysis requested{{/if}}
{{#if quality_focus}}- ✨ Quality improvement focus{{/if}}

Proceeding with comprehensive documentation audit...
</transformation_feedback>
</prompt_transformation>

<thinking_process>
<!-- Use enhanced thinking blocks component -->
<extended_thinking>
  <understanding_phase>
    <user_intent>
    Let me understand what you're asking for:
    - Primary goal: Audit documentation and create improvement plan
    - Context: Evaluating current state and planning enhancements
    - Constraints: Must follow best practices and be AI-friendly
    - Success looks like: Comprehensive documentation strategy
    </user_intent>
    
    <assumptions>
    I'm making these assumptions:
    - Documentation quality impacts development velocity
    - AI-friendly documentation is a priority
    - Both current state and future needs matter
    - Documentation should be versioned separately
    </assumptions>
  </understanding_phase>
  
  <analysis_phase>
    <current_state>
    Current situation:
    - Assessing existing documentation coverage
    - Identifying documentation gaps
    - Evaluating documentation quality
    </current_state>
    
    <options_considered>
    Possible documentation strategies:
    1. Incremental improvement: Fix gaps gradually
    2. Complete overhaul: Rebuild from scratch
    3. Hybrid approach: Salvage good, rebuild bad
    </options_considered>
    
    <decision_rationale>
    Choosing approach based on:
    - Current documentation state
    - Project complexity and maturity
    - Team size and resources
    </decision_rationale>
  </analysis_phase>
  
  <planning_phase>
    <execution_plan>
    Here's my audit plan:
    1. Scan codebase for existing documentation
    2. Analyze code complexity and documentation needs
    3. Identify missing documentation areas
    4. Evaluate documentation quality
    5. Create prioritized improvement plan
    </execution_plan>
    
    <risk_mitigation>
    Potential issues and mitigations:
    - Risk: Documentation drift → Mitigation: Automated checks
    - Risk: Over-documentation → Mitigation: Focus on value
    - Risk: Under-documentation → Mitigation: Coverage metrics
    </risk_mitigation>
    
    <success_metrics>
    How we'll know documentation is good:
    - [ ] All public APIs documented
    - [ ] Architecture clearly explained
    - [ ] Onboarding guides complete
    - [ ] AI can understand codebase
    </success_metrics>
  </planning_phase>
  
  <analytical_thinking>
    <data_synthesis>
    Documentation patterns discovered:
    - Current documentation locations
    - Documentation format consistency
    - Coverage gaps and overlaps
    </data_synthesis>
    
    <gap_analysis>
    Missing documentation elements:
    - API reference completeness
    - Architecture decision records
    - Development workflows
    - Deployment procedures
    </gap_analysis>
  </analytical_thinking>
  
  <pattern_recognition>
  Documentation patterns to apply:
  - README structure standards
  - API documentation format
  - Tutorial progression
  - Example organization
  </pattern_recognition>
  
  <critical_evaluation>
    <potential_issues>
    What could go wrong:
    - Documentation becomes stale quickly
    - Too much detail overwhelms readers
    - Not enough detail confuses users
    </potential_issues>
    
    <oversimplifications>
    What I might be oversimplifying:
    - Maintenance effort required
    - Different audience needs
    - Documentation tooling complexity
    </oversimplifications>
    
    <skeptical_review>
    A skeptical reviewer would point out:
    - "Will anyone actually maintain this?"
    - "Is this level of detail necessary?"
    - "How do we keep it synchronized?"
    </skeptical_review>
    
    <confidence_assessment>
    My confidence level: High
    Because: Clear patterns for good documentation exist
    Areas of uncertainty: Long-term maintenance commitment
    </confidence_assessment>
  </critical_evaluation>
  
  <thinking_summary>
  ## 🧠 My Thinking Process
  
  **Understanding**: Auditing documentation completeness and quality
  
  **Analysis**: Identifying gaps and improvement opportunities
  
  **Approach**: Systematic audit with prioritized improvement plan
  
  **Next Steps**: Scan codebase and analyze documentation state
  </thinking_summary>
</extended_thinking>
</thinking_process>

<initial_analysis_phase>
Before creating the plan, you MUST:

1. **Launch analysis tasks** to comprehensively audit the codebase:
   
   **Task 1: Analyze repository structure and technology stack**
   - Identify all repositories/packages in the working directory
   - Determine technology stack for each component
   - Map out inter-repository dependencies
   - Identify existing documentation locations
   
   **Task 2: Audit existing documentation**
   - Find all .md files (excluding node_modules, .git, etc.)
   - Assess documentation quality and completeness
   - Identify documentation patterns and standards
   - Catalog what's documented vs. what's missing
   
   **Task 3: Analyze codebase functionality**
   - Understand core features and components
   - Map API endpoints and data flows
   - Identify architectural patterns
   - Determine deployment configurations
   
   **Task 4: Evaluate developer experience**
   - Assess ease of onboarding
   - Review example code availability
   - Check for testing documentation
   - Identify pain points and gaps

2. **Synthesize findings** from all tasks into a comprehensive understanding

3. **Reference the documentation specification** at ~/Developer/docs/apps/docs.md for best practices
</initial_analysis_phase>

<planning_requirements>
After analysis, create a detailed implementation plan that:

1. **Follows the specification** from ~/Developer/docs/apps/docs.md exactly
2. **Organized efficiently** with independent tasks that can be executed systematically
3. **Provides concrete deliverables** for each task with examples
4. **Estimates effort realistically** based on codebase size and complexity
5. **Prioritizes impact** - most valuable documentation first
6. **Considers existing content** - migrate and improve rather than recreate
</planning_requirements>

<goal>
$ARGUMENTS
</goal>

<output_structure>
Create a comprehensive plan with:

## Documentation Audit Report

### Current State Analysis
- Repository structure and components
- Existing documentation coverage (percentage and quality score)
- Technology stack summary
- Key features and functionality
- Documentation gaps and pain points

### Recommendations Summary
- High-priority improvements
- Quick wins vs. long-term investments
- Resource requirements

## Implementation Plan

### Phase 1: Foundation Tasks

#### Task 1: Repository Setup
**Description**: Create [projectName]-docs repository with standard structure

**Deliverables**:
- Initialize repository with .docindex.json
- Create directory structure per specification
- Set up CI/CD for validation
- Configure automated checks

**Estimated Effort**: 0.5 developer days
**Dependencies**: None (can start immediately)

#### Task 2: Architecture Documentation
**Description**: Document system architecture and technology stack

**Deliverables**:
- architecture/overview.md with system diagrams
- architecture/stack.md with version matrix
- architecture/data-flow.md with flow diagrams
- ADRs for key decisions

**Estimated Effort**: 2 developer days
**Dependencies**: None (can start immediately)

#### Task 3: API Documentation
**Description**: Complete API reference documentation

**Deliverables**:
- api/rest.md with all endpoints
- api/authentication.md with auth flows
- api/errors.md with error codes
- api/examples/ with code samples

**Estimated Effort**: 3 developer days
**Dependencies**: None (can start immediately)

### Phase 2: Development & Operations Tasks

[Continue with similar task breakdowns...]

### Phase 3: Enhancement & Polish

[Final tasks for completeness...]

## Execution Timeline

**Week 1**: Phase 1 - Foundation tasks
**Week 2**: Phase 2 - Development and operations docs
**Week 3**: Phase 3 - Polish and enhancement
**Week 4**: Review, testing, and deployment

## Success Metrics

- [ ] 95%+ API coverage documented
- [ ] All code examples tested and working
- [ ] Documentation health score >90%
- [ ] AI tool compatibility verified
- [ ] Team onboarding time reduced by 50%

## Resource Requirements

- **Human Resources**: X developer days total
- **Tools**: List any required tools/services
- **Budget**: Any paid services needed

### ⚠️ Caveats & Limitations
- **Assumptions made**: 
  - Documentation will be actively maintained
  - Team has capacity for documentation work
  - Current codebase is stable enough to document
  - Developers value and will use documentation
- **Not addressed**: 
  - Documentation versioning strategy
  - Multi-language/localization needs
  - External API consumer needs
  - Legal/compliance documentation requirements
- **Technical debt**: 
  - May not catch all undocumented edge cases
  - Quality assessment is somewhat subjective
  - Automated documentation may lack context
- **Alternative approaches**: 
  - Documentation generation tools (JSDoc, etc.)
  - Wiki-based systems (Confluence, etc.)
  - Documentation-as-code generators
  - Outsourcing to technical writers

</output_structure>

<planning_principles>
- Every task should be independently executable
- Include specific file paths and examples
- Provide templates and patterns to follow
- Consider both creation and migration paths
- Optimize for AI-assisted development
- Ensure documentation remains a living resource
- Plan for automation and validation
- Consider the full developer journey
</planning_principles>

<task_template>
#### Task [Number]: [Descriptive Name]
**Description**: [Clear description of what this task accomplishes]

**Deliverables**:
- [Specific file/document to create/update]
- [Another deliverable with details]

**Implementation Notes**:
- [Key consideration or approach]
- [Important pattern to follow]

**Example Structure**:
[Show a brief example of expected output]

**Estimated Effort**: [X developer days]
**Dependencies**: [None | Task Y must complete first]

**Success Criteria**:
- [ ] [Measurable outcome]
- [ ] [Another measurable outcome]
</task_template>

<execution_notes>
1. Start with analysis tasks to understand the full scope
2. Create tasks that can be assigned to different team members
3. Provide enough detail that someone unfamiliar with the codebase can execute
4. Include quality checks and validation steps
5. Plan for iterative improvement, not perfection
6. Consider documentation as code - testable and maintainable
</execution_notes>
</documentation_audit_directive>

<context_output>
## 🔗 Command Context
**Command**: /user:docs
**Timestamp**: [Current ISO timestamp]
**Session**: `.claude/session/current/`

**Key Findings**:
- Current documentation coverage
- Critical gaps identified
- Priority improvements
- Implementation timeline
- Resource requirements

**For Next Commands**:
```json
{
  "command": "docs",
  "coverage_percentage": "[current-coverage]",
  "priority_gaps": "[critical-missing-docs]",
  "estimated_effort": "[total-days]",
  "documentation_path": "[projectName]-docs/",
  "phase": "audit_complete",
  "suggested_next": [
    "/user:build - Implement documentation plan",
    "/user:create - Generate missing docs",
    "/user:multitask - Execute parallel doc tasks",
    "/user:design - Document design system"
  ]
}
```
</context_output>

Begin by acknowledging the audit request and current working directory, then launch the analysis tasks. After receiving all results, synthesize findings and create the comprehensive implementation plan.