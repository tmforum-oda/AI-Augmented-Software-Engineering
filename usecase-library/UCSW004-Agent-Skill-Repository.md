# UCSW004: ODA Agent Skill Repository

This use case describes an **Agent Skill repository** for TM Forum Open Digital Architecture components and operators.

The approach is modeled on two example skills repositories :
* [Hugging Face Skills repository](https://github.com/huggingface/skills) which provides AI coding agents with domain-specific skills for ML tasks like dataset creation, model training, and evaluation. 
* [Vercel - React best practices](https://vercel.com/blog/introducing-react-best-practices) which provides best-bractice guidance on building User Interfaces using React.

This use case adapts that pattern for TM Forum ODA development, enabling skills for Open API implementation, component design, and standards alignment.

It is based on the following assumptions:
- Developers use AI coding agents (Claude Code, Codex, Cursor, GitHub Copilot etc.)
- Skills provide domain-specific guidance for ODA development
- Skills are interoperable across different agent platforms

---

## Skill Discovery and Activation

The AI agent discovers and activates relevant skills based on developer intent.

### Prerequisites
- Agent Skill repository registered with the coding agent
- Skills indexed via SKILL.md files with name and description

### How to
1. The developer describes their task (e.g., "implement TMF620 API")
2. The agent matches intent to available skill descriptions
3. The agent loads the relevant SKILL.md instructions
4. The agent follows skill guidance to assist the developer

### Validation
- Agent correctly identifies when to activate ODA-specific skills
- Agent follows skill instructions for TM Forum standards alignment

---

## Proposed ODA Skills

Skills covering core ODA development scenarios:

| Skill | Purpose |
|-------|---------|
| oda-open-api | Implement TM Forum Open APIs with code generation and CTK validation |
| oda-component-design | Design ODA Component YAML specifications |
| oda-sid-modeling | Work with SID entities for database and data model design |
| oda-etom-mapping | Map business requirements to eTOM processes |
| oda-canvas-operator | Develop ODA Canvas operators and controllers |
| oda-responsible-ai | Embed Responsible AI practices for telecom AI |

*example skills - the repository should grow and improve over time.
---

## Multi-Agent Compatibility

Agent skills is an open standard (https://agentskills.io/).Skills work across different AI coding agent platforms.

### Supported Agents
- **Claude Code**: Plugin marketplace registration
- **OpenAI Codex**: AGENTS.md discovery file
- **Gemini CLI**: Extension configuration
- **Cursor/Windsurf/GitHub Copilot**: Direct SKILL.md file reading

### How to
- Repository provides integration files for each agent platform
- Agents discover skills through platform-specific mechanisms
- Skills execute identically regardless of agent platform

### Validation
- Same skill produces consistent results across different agents
- Installation instructions work for each supported platform
