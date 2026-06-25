# Agentic Skills

A curated repository of custom skills designed for AI agents and coding assistants. These skills extend agent capabilities in specialized domains, including technical interview preparation, resume engineering, and professional profile optimization.

## Core Architecture

Agentic skills are modular instruction sets that are dynamically discovered, loaded, and triggered by the agent based on the user's intent. 

Each skill is structured as a directory containing a `SKILL.md` file:

- **YAML Frontmatter**: Contains the `name` of the skill and a detailed `description` used by the agent's router to match user requests.
- **Markdown Body**: Contains the specialized execution instructions, protocols, and context that guide the agent's behavior once the skill is activated.

### Directory Structure

```text
agentic-skills/
├── README.md
└── skills/
    ├── interview/
    │   ├── base-interviewer/
    │   │   └── SKILL.md
    │   ├── behavioral-interviewer/
    │   │   └── SKILL.md
    │   ├── dsa-interviewer/
    │   │   └── SKILL.md
    │   ├── hld-interviewer/
    │   │   └── SKILL.md
    │   └── lld-interviewer/
    │       └── SKILL.md
    ├── linkedin/
    │   └── linkedin-optimizer/
    │       └── SKILL.md
    └── resume/
        └── resume-builder/
            └── SKILL.md
```

---

## Skill Registry

The repository is organized into specialized suites.

### 1. Interview Preparation Suite (`skills/interview/`)

A system designed to conduct interactive, turn-by-turn mock interviews. It adapts to candidate experience levels (from Intern to Senior Principal) and dynamically incorporates target company specifications via web research.

| Skill Name | Path | Description |
| :--- | :--- | :--- |
| **base-interviewer** | `skills/interview/base-interviewer` | The primary orchestrator. Manages candidate intake, designs the interview plan, conducts resume validation, coordinates specialized rounds, and generates the final evaluation report. |
| **dsa-interviewer** | `skills/interview/dsa-interviewer` | Conducts interactive Data Structures & Algorithms interviews. Focuses on complexity, trade-offs, and advanced optimizations (e.g., lock-free concurrency, cache-locality) for senior roles. |
| **hld-interviewer** | `skills/interview/hld-interviewer` | Conducts interactive System Design / High-Level Design (HLD) interviews. Evaluates scalability, fault tolerance, and petabyte-scale architectural resilience. |
| **lld-interviewer** | `skills/interview/lld-interviewer` | Conducts interactive Low-Level Design (LLD) and Object-Oriented Design (OOD) interviews. Evaluates SOLID principles, design patterns, and concurrency considerations. |
| **behavioral-interviewer** | `skills/interview/behavioral-interviewer` | Conducts interactive Behavioral & Leadership interviews. Assesses collaboration, ownership, systemic cross-organizational impact, and conflict resolution. |

### 2. Career & Personal Branding Suite

Tools to optimize professional representation across application channels.

| Skill Name | Path | Description |
| :--- | :--- | :--- |
| **resume-builder** | `skills/resume/resume-builder` | Generates ATS-optimized resumes in DOCX and PDF formats. Translates career history into achievement-dense, quantified bullet points using industry-standard verb structures. |
| **linkedin-optimizer** | `skills/linkedin/linkedin-optimizer` | Optimizes LinkedIn profiles for recruiter visibility and personal branding. Enhances headlines, summaries, and experience sections based on background materials. |

---

## Installation & Usage

### Adding Skills via CLI (Recommended)

You can add these skills to your workspace using the `skills` CLI:

- **Interactive Selection**: Run this command to list all available skills in the repository and select the ones to add:
  ```bash
  npx skills add sriram789/agentic-skills
  ```

- **Add an Individual Skill**: To add a specific skill directly, use the `--skill` flag:
  ```bash
  npx skills add sriram789/agentic-skills --skill your-skill-name
  ```

### Manual Installation

To manually install these skills, place the skill directories in one of the recognized customization roots.

#### Global Installation

To make skills available across all projects, copy the skill directories to your global configuration directory:

```bash
cp -r skills/* ~/.gemini/config/skills/
```

#### Project-Scoped Installation

To activate skills only for a specific workspace, copy them to a `.agents/skills/` directory at the root of the workspace:

```bash
mkdir -p .agents/skills/
cp -r skills/* .agents/skills/
```

---

## Authoring Custom Skills

You can extend this repository or create your own skills by adhering to the following specification.

### 1. File Template (`SKILL.md`)

Create a `SKILL.md` file inside your new skill directory:

```markdown
---
name: your-skill-name
description: >
  A detailed description of when this skill should trigger. Mention key terms, user scenarios, and file types that indicate this skill is relevant.
---

# Skill Title

Detailed instructions for the agent. Specify:
- The exact persona and tone to adopt.
- The step-by-step workflow to execute.
- Expected inputs and outputs.
- Verification and checking protocols.
```

### 2. Best Practices

- **Clear Activation Criteria**: Write a descriptive description in the YAML frontmatter. The routing model relies on this description to decide when to activate the skill.
- **Keep Instructions Modular**: Keep the main `SKILL.md` file under 500 lines. If the skill requires extensive reference material or scripts, organize them into subdirectories:
  - `scripts/` - Helper scripts and utilities.
  - `examples/` - Reference implementations and usage patterns.
  - `resources/` - Additional templates or static assets.
  - `references/` - Additional documentation.
- **Micro-Interactive Protocols**: For interactive tasks (such as mock interviews), instruct the agent to ask questions sequentially (one at a time) rather than overloading the user.

---

## Contributing

1. Fork the repository.
2. Create a feature branch for your new skill or enhancement.
3. Ensure the skill directory structure follows the standard layout.
4. Verify that the YAML frontmatter in `SKILL.md` is valid and descriptive.
5. Submit a pull request with a description of the skill and its target use cases.

## License

This project is licensed under the MIT License.
