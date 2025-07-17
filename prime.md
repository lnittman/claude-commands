# Prime Session Context Command

Start every Claude Code session with comprehensive project understanding and optimal context.

<session_priming_directive>
You are tasked with quickly and efficiently priming the context for a Claude Code session by understanding the current project state, recent changes, documentation, and development patterns. This command should be run at the start of every session to ensure Claude has the full picture.

<components>
  <use>@session-state</use>
  <use>@xml-transformer</use>
  <use>@thinking-blocks</use>
  <use>@verification-patterns</use>
  <use>@output-standards</use>
</components>

<references>
@file:~/Developer/docs/apps/docs.md
@file:~/Developer/docs/apps/patterns.md
@file:~/Developer/docs/tools/claude-code-power-user.md
@file:~/Developer/docs/tools/claude-command-center.md
</references>

<session_management>
<!-- Use session-state component -->
<session_init>
  <check_existing>true</check_existing>
  <create_if_missing>true</create_if_missing>
  <archive_old_sessions>true</archive_old_sessions>
  <load_preferences>true</load_preferences>
</session_init>

<context_loading>
  <skip_if_recent>true</skip_if_recent>
  <recent_threshold_minutes>30</recent_threshold_minutes>
  <always_refresh>["git_status", "recent_commits"]</always_refresh>
</context_loading>
</session_management>

<universal_input_handler>
Process $ARGUMENTS to detect and handle:

**URLs Detected:**
- Documentation sites → Extract setup patterns, dependencies
- GitHub repos → Clone and analyze structure
- Blog posts → Extract relevant techniques
- Stack Overflow → Understand solutions

**Code Blocks Detected:**
- Error messages → Diagnose issues
- Configuration → Understand setup
- Command output → Parse results

**File Paths Detected:**
- Read and analyze specified files
- Extract relevant patterns
- Focus analysis on those areas

**Screenshots/Images Detected:**
- UI screenshots → Understand current state
- Error screenshots → Diagnose issues
- Architecture diagrams → Understand structure

**Mixed Content:**
- Separate by type and process each
- Combine insights for comprehensive view
- Prioritize actionable information
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
<!-- Use enhanced thinking blocks component -->
<extended_thinking>
  <understanding_phase>
    <user_intent>
    Let me understand what you're asking for:
    - Primary goal: Prime Claude with comprehensive project context
    - Context: Starting a new session or refreshing understanding
    - Constraints: Be efficient but thorough
    - Success looks like: Complete awareness of project state
    </user_intent>
    
    <assumptions>
    I'm making these assumptions:
    - You want a quick but comprehensive overview
    - Recent changes are most important
    - Pattern recognition helps future work
    - Context from previous sessions may be relevant
    </assumptions>
  </understanding_phase>
  
  <analysis_phase>
    <current_state>
    Current situation:
    - Checking for existing session context
    - Identifying what needs refreshing
    - Determining focus areas from input
    </current_state>
    
    <options_considered>
    Possible priming approaches:
    1. Full scan: Complete project analysis
    2. Incremental: Focus on changes since last session
    3. Targeted: Prime specific areas mentioned
    </options_considered>
    
    <decision_rationale>
    Choosing approach based on:
    - Time since last session
    - Scope of recent changes
    - User's specific focus areas
    </decision_rationale>
  </analysis_phase>
  
  <planning_phase>
    <execution_plan>
    Here's my priming plan:
    1. Load or create session context
    2. Analyze project structure and patterns
    3. Review recent changes and commits
    4. Identify active work areas
    5. Synthesize actionable insights
    </execution_plan>
    
    <risk_mitigation>
    Potential issues and mitigations:
    - Risk: Information overload → Mitigation: Focus on relevance
    - Risk: Missing context → Mitigation: Systematic scanning
    - Risk: Stale assumptions → Mitigation: Verify against current state
    </risk_mitigation>
    
    <success_metrics>
    How we'll know priming worked:
    - [ ] Project structure understood
    - [ ] Recent changes identified
    - [ ] Patterns recognized
    - [ ] Ready for productive work
    </success_metrics>
  </planning_phase>
  
  <execution_thinking>
    <pre_flight_check>
    Before proceeding:
    - [ ] Session directory accessible
    - [ ] Git repository detected
    - [ ] Documentation available
    - [ ] Previous context loadable
    </pre_flight_check>
    
    <execution_opportunities>
    Can analyze systematically:
    - Project structure scan
    - Git history analysis
    - Documentation review
    - Pattern extraction
    </execution_opportunities>
  </execution_thinking>
  
  <pattern_recognition>
  Looking for patterns in:
  - Code organization and architecture
  - Development workflows
  - Technology choices
  - Documentation style
  </pattern_recognition>
  
  <critical_evaluation>
    <potential_issues>
    What could go wrong:
    - Overwhelming detail: Medium risk
    - Missing recent changes: Low risk
    - Incorrect pattern inference: Low risk
    </potential_issues>
    
    <oversimplifications>
    What I might be oversimplifying:
    - Project complexity and interdependencies
    - Team dynamics and preferences
    - Historical context for decisions
    </oversimplifications>
    
    <skeptical_review>
    A skeptical reviewer would point out:
    - "Is all this context actually needed?"
    - "Are we making correct assumptions?"
    - "Could we be more focused?"
    </skeptical_review>
    
    <confidence_assessment>
    My confidence level: High
    Because: Systematic approach to context gathering
    Areas of uncertainty: Implicit project conventions
    </confidence_assessment>
  </critical_evaluation>
  
  <thinking_summary>
  ## 🧠 My Thinking Process
  
  **Understanding**: Priming Claude with complete project awareness
  
  **Analysis**: Balancing thoroughness with efficiency
  
  **Approach**: Systematic scanning with focus on recent changes
  
  **Next Steps**: Load context and analyze project state
  </thinking_summary>
</extended_thinking>
</thinking_process>

<analysis_phase>
  - Primary goal: {{extracted_goal || "Initialize session with project context"}}
  - Focus area: {{focus_area || "General project understanding"}}
  - Session state: {{new_session || "Continuing existing session"}}
  </user_intent>
  
  <assumptions>
  I'm assuming:
  - You want comprehensive project understanding
  - Recent changes are important to highlight
  - Documentation state matters for context
  - Development patterns should guide future work
  </assumptions>
</understanding_phase>

<analysis_phase>
  <current_state>
  Analyzing project state:
  - Repository location: {{repo_path}}
  - Last session: {{last_session_time || "First session"}}
  - Context freshness: {{context_age}}
  </current_state>
  
  <approach_selection>
  Priming strategy:
  1. Quick scan: Fast overview of key files
  2. Deep dive: Comprehensive analysis of all aspects
  3. Focused: Specific area exploration
  
  Selecting: {{selected_approach}} based on {{reason}}
  </approach_selection>
</analysis_phase>

<planning_phase>
  <execution_plan>
  My analysis plan:
  1. Check session state and load existing context
  2. Scan for recent changes and activity
  3. Analyze project structure and patterns
  4. Synthesize findings into actionable context
  </execution_plan>
  
  <success_metrics>
  Context will be primed when:
  - [ ] Project structure is mapped
  - [ ] Recent activity is understood
  - [ ] Development patterns are identified
  - [ ] Next actions are clear
  </success_metrics>
</planning_phase>

<thinking_summary>
## 🧠 Approach

**Understanding**: {{session_goal_summary}}

**Strategy**: {{selected_prime_strategy}}

**Focus**: {{what_to_emphasize}}

Initiating comprehensive context analysis...
</thinking_summary>
</thinking_process>

<verification_phase>
<!-- Use verification patterns component -->
<pre_execution_verification>
  <action_summary>
    <description>Analyze project and load context</description>
    <impact_level>low</impact_level>
    <reversibility>fully</reversibility>
  </action_summary>
  
  <analysis_scope>
    <will_examine>
      - Project structure and files
      - Git history and status
      - Documentation coverage
      - Code patterns and quality
    </will_examine>
    
    <will_not_modify>
      - No files will be changed
      - No commands will be executed
      - Only reading and analysis
    </will_not_modify>
  </analysis_scope>
</pre_execution_verification>

<user_confirmation>
## ✅ Prime Analysis

**About to**: Analyze your project and establish session context

**This will examine**:
- Project structure and technology stack
- Recent git activity and changes  
- Documentation state and patterns
- Code quality indicators

**Safe operation**: Read-only analysis, no modifications.

*Starting analysis...*
</user_confirmation>
</verification_phase>

<analysis_phase>
Launch analysis tasks to comprehensively understand the project:

**Task 1: Documentation Discovery**
- Find and read all CLAUDE.md files (project and user)
- Locate [projectName]-docs/ repository if it exists
- Read all README files in the project
- Check for .docindex.json for AI navigation
- Identify documentation patterns and standards

**Task 2: Project Structure Analysis**
- Map repository structure (monorepo, packages, apps)
- Identify technology stack and frameworks
- Find configuration files (package.json, tsconfig, etc.)
- Understand build and deployment setup
- Check for testing infrastructure

**Task 3: Recent Activity Analysis**
- git log --oneline -30 (recent commits)
- git diff HEAD~5 (recent changes)
- git branch -a (active branches)
- git status (current state)
- Identify work in progress

**Task 4: Code State Assessment**
- Check for TODO/FIXME comments
- Identify incomplete features
- Review error logs if available
- Assess code quality patterns
- Find performance bottlenecks

$FOCUS
</analysis_phase>

<synthesis_requirements>
After analysis, synthesize findings into a comprehensive context prime that includes:

1. **Project Overview**
   - Name and purpose
   - Technology stack with versions
   - Architecture pattern (monorepo, microservices, etc.)
   - Current development phase

2. **Recent Activity Summary**
   - Last 5-10 meaningful commits
   - Active feature development
   - Recent bug fixes or issues
   - Who's been working on what

3. **Documentation State**
   - Coverage percentage estimate
   - Quality assessment
   - Missing critical docs
   - Alignment with ~/Developer/docs standards

4. **Development Priorities**
   - Work in progress
   - Blocked items
   - Technical debt
   - Performance concerns

5. **Quick Start Actions**
   - Common commands for this project
   - Current branch strategy
   - Testing approach
   - Deployment process
</synthesis_requirements>

<focus_handling>
If user provides a focus argument:
- Adjust analysis tasks to deep dive on that area
- Provide specialized context for the focus topic
- Suggest relevant files and documentation
- Outline specific challenges in that domain

Focus examples:
- "authentication" → Auth flow, user management, security
- "performance" → Metrics, bottlenecks, optimization opportunities  
- "testing" → Coverage, missing tests, testing patterns
- "ui/ux" → Design system, components, user flows
- "api" → Endpoints, data flow, integration points
</focus_handling>

<output_format>
## 🚀 Project Context Primed: [Project Name]

### 📊 Quick Stats
- **Tech Stack**: [Primary technologies]
- **Project Type**: [Web app, API, Library, etc.]
- **Development Phase**: [Alpha, Beta, Production]
- **Documentation Health**: [Score/100]

### 📈 Recent Activity
[Recent meaningful commits with context]

### 🎯 Current Focus Areas
1. **[Feature/Area]**: [Brief status and next steps]
2. **[Feature/Area]**: [Brief status and next steps]
3. **[Feature/Area]**: [Brief status and next steps]

### ⚡ Quick Commands
**Development**: [project-specific dev command]
**Testing**: [project-specific test command]
**Build**: [project-specific build command]

### 📋 Priority Tasks
- [ ] [High priority task with context]
- [ ] [Another priority task]
- [ ] [Third priority task]

### 🔧 Workspace Setup
- **Current Branch**: [branch name]
- **Working Directory**: [path]
- **Related Repos**: [if applicable]

### 💡 Context Notes
[Any special considerations, patterns, or warnings specific to this project]

$FOCUS_OUTPUT

### ⚠️ Caveats & Limitations
- **Assumptions made**: 
  - Git repository structure is standard
  - Documentation follows common patterns
  - Recent activity reflects current priorities
  - Session state persists between runs
- **Not addressed**: 
  - Private/proprietary documentation
  - Team communication context (Slack, etc.)
  - External service dependencies
  - Local environment specifics
- **Technical debt**: 
  - May miss nuanced project conventions
  - Can't access runtime state or logs
  - Limited to static code analysis
- **Alternative approaches**: 
  - Manual project walkthrough
  - Team knowledge transfer session
  - Reading project wiki/confluence
  - Pair programming for context

---
*Session primed. Ready for development!*

<context_output>
## 🔗 Command Context
**Command**: /user:prime
**Timestamp**: [Current ISO timestamp]
**Session**: `.claude/session/current/`

**Key Findings**:
- Project: [Project name and type]
- Stack: [Primary technologies]
- Phase: [Current development phase]
- Focus: [Main areas of activity]

**For Next Commands**:
- Command: prime
- Project name: [name]
- Tech stack:
  - Frontend: [framework]
  - Backend: [framework]
  - Database: [type]
- Current focus: [area]
- Suggested next:
  - /user:build [specific task]
  - /user:vision explore [feature]
  - /user:design review components
</context_output>
</output_format>

<no_focus_output>
If no focus argument provided, add this section:

### 🎯 What would you like to focus on today?

**High-Impact Areas:**
1. 🔥 **[Area]** - [Why it's important]
2. 🚧 **[Area]** - [Current blocker or challenge]
3. ✨ **[Area]** - [Opportunity for improvement]

**Quick Wins Available:**
- Fix: [Specific issue that can be resolved quickly]
- Improve: [Performance or quality enhancement]
- Document: [Missing documentation that's needed]

**Strategic Initiatives:**
- [ ] [Longer-term improvement]
- [ ] [Architectural enhancement]
- [ ] [Technical debt reduction]

*Tip: Re-run with `/user:prime focus on [area]` for deep context on any topic*
</no_focus_output>

<best_practices>
1. Keep analysis fast - this runs at session start
2. Focus on actionable intelligence
3. Highlight what's changed since last session
4. Make connections to existing patterns
5. Suggest concrete next steps
6. Reference team conventions from CLAUDE.md
7. Surface hidden issues or opportunities
8. Keep output scannable and useful
</best_practices>
</session_priming_directive>

$ARGUMENTS