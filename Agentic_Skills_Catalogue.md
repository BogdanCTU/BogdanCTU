# Claude Code Skills, Plugins & Engineering Resources

A curated catalogue of the repositories supplied for development, interface design, documentation, and interview preparation.

> **Scope note:** These repositories are not all Claude Code plugins in the strict sense. Some are installable Claude Code plugins or Agent Skills; others are standalone developer tools, reusable project guidelines, or learning resources. The distinction is called out below so the catalogue does not imply that every repository can be installed with `/plugin`.

## At a glance

| Area | Repository | Primary role | Claude Code integration |
|---|---|---|---|
| Development | [mattpocock/skills](https://github.com/mattpocock/skills) | Practical engineering workflows and agent skills | Claude plugin |
| Development | [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | Lean implementation, code review, and engineering discipline | Claude plugin |
| Development | [obra/superpowers](https://github.com/obra/superpowers) | Structured, skill-driven software development methodology | Claude plugin |
| Development | [affaan-m/ECC](https://github.com/affaan-m/ECC) | Broad agent-harness toolkit: skills, agents, hooks, commands, and tooling | Claude Code-oriented toolkit |
| Development | [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) | Guidelines for disciplined, simple, goal-driven coding | `CLAUDE.md` guidance |
| Design | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Design vocabulary, critique, polish, and interface audits | Installable agent plugin/skills |
| Design | [Nutlope/hallmark](https://github.com/Nutlope/hallmark) | High-quality visual design, theme selection, redesign, and design QA | Claude Code skill |
| Design | [wheresryan22/anatomy](https://github.com/wheresryan22/anatomy) | Interactive visual explanations built as detailed SVG/WebGL/3D objects | Claude Code skill |
| Documentation | [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design) | Brand-aware technical and editorial diagrams | Claude Code plugin / Agent Skill |
| Documentation | [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | Codebase and knowledge graph generation for agent context | CLI that installs an agent skill |
| Documentation | [microsoft/markitdown](https://github.com/microsoft/markitdown) | Convert office files and other formats into Markdown | Standalone CLI/Python library; not a Claude skill |
| Interviews | [jwasham/coding-interview-university](https://github.com/jwasham/coding-interview-university) | Computer science and coding interview study plan | Reference material; not a Claude skill |
| Interviews | [donnemartin/system-design-primer](https://github.com/donnemartin/system-design-primer) | System design concepts, architecture patterns, and interview practice | Reference material; not a Claude skill |

---

## 1. Development

### 1.1 [Matt Pocock — Skills for Real Engineers](https://github.com/mattpocock/skills)

**Purpose:** A collection of small, composable agent skills intended to improve real-world software engineering rather than encourage unstructured code generation.

**What it provides**
- Requirements clarification and alignment through `/grill-me` and `/grill-with-docs`.
- Shared project vocabulary and documentation of decisions.
- Engineering workflows designed to reduce misunderstandings and unnecessary implementation.
- Skills grouped around engineering and productivity.

**Why use it:** Useful at the start of a feature or change to clarify requirements, establish terminology, and keep the agent aligned with the project.

**Claude Code installation**
```bash
claude plugin install mattpocock-skills@claude-plugins-official
```

The repository also documents installation through other agent ecosystems. Choose either the plugin route or a skills-file installer for a given agent; do not install both for the same agent.

### 1.2 [Ponytail](https://github.com/DietrichGebert/ponytail)

**Purpose:** A senior-engineer-style coding agent skill focused on doing only the work required while preserving correctness, security, tests, and maintainability.

**What it provides**
- Lean implementation that reuses existing project components and conventions.
- Review of changes for bugs, security issues, performance, test gaps, and unnecessary code.
- Repository-level audit capabilities.
- Configurable operating modes, including `lite`, `full`, `ultra`, and `off`.

**Why use it:** A useful counterweight to overengineering. It encourages the agent to inspect the existing codebase before adding abstractions or dependencies, and to review the wider impact of a change rather than only the diff.

**Claude Code installation**
```text
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

Example commands:
```text
/ponytail
/ponytail-review
/ponytail-audit
```

### 1.3 [Superpowers](https://github.com/obra/superpowers)

**Purpose:** A complete, skill-driven software development methodology for coding agents.

**What it provides**
- Requirements discovery and specification before implementation.
- Design review and implementation planning.
- Test-driven development, including red/green/refactor discipline.
- Subagent-driven implementation and review workflows.
- Structured debugging and other repeatable engineering practices.

**Why use it:** Best suited to substantial features or multi-step engineering tasks where a defined process, explicit approval points, tests, and review are valuable.

**Claude Code installation**
```text
/plugin install superpowers@claude-plugins-official
```

The repository also documents an alternative marketplace:
```text
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

### 1.4 [Everything Claude Code (ECC)](https://github.com/affaan-m/ECC)

**Purpose:** A broad toolkit for configuring and extending coding-agent workflows. It is more than a single skill: the repository combines agent instructions and reusable workflow components.

**What it provides**
- Skills and specialized agents.
- Commands and workflow automation.
- Hooks and configuration patterns.
- Development, review, and productivity tooling.
- Supporting utilities and integrations.

**Why use it:** Consider ECC when building a more comprehensive Claude Code environment with reusable agents, automated checks, and configurable workflows. Its breadth makes it worth reviewing selectively rather than enabling every component by default.

**Integration note:** Follow the repository's current installation instructions and select the components that match the project. Review hooks, scripts, permissions, and external integrations before enabling them.

### 1.5 [Andrej Karpathy-inspired Claude Code Guidelines](https://github.com/multica-ai/andrej-karpathy-skills)

**Purpose:** A compact `CLAUDE.md` instruction set derived from Andrej Karpathy's observations about common LLM coding failures.

**Four core principles**
1. **Think Before Coding** — state assumptions, identify ambiguity, surface trade-offs, and ask questions when necessary.
2. **Simplicity First** — implement the smallest solution that satisfies the requirement; avoid speculative abstractions.
3. **Surgical Changes** — avoid unrelated refactoring or edits outside the requested scope.
4. **Goal-Driven Execution** — define verifiable success criteria and validate the result.

**Why use it:** A lightweight baseline for improving day-to-day agent behaviour, especially when the agent tends to make assumptions, overcomplicate solutions, or modify unrelated code.

**Integration note:** This repository is primarily a `CLAUDE.md` guideline file, not a conventional plugin marketplace package. Review the file and incorporate its instructions into the appropriate project-level Claude Code instructions.

---

## 2. Design

### 2.1 [Impeccable](https://github.com/pbakaus/impeccable)

**Purpose:** A design vocabulary and set of workflows that help coding agents make more intentional interface decisions.

**What it provides**
- Commands to steer visual design, such as `bolder`, `quieter`, `distill`, `colorize`, and `typeset`.
- Design critique and audit workflows.
- Accessibility, responsive behaviour, performance, and theming checks.
- A way to document the product and existing design system for subsequent work.

**Why use it:** Particularly useful when refining an existing UI. It gives the agent more precise design direction than generic requests such as “make this look better.”

**Installation**
```bash
npx impeccable install
```

Then initialize the project:
```text
/impeccable init
```

### 2.2 [Hallmark](https://github.com/Nutlope/hallmark)

**Purpose:** A design skill intended to produce distinctive, product-oriented interfaces rather than generic AI-generated layouts.

**What it provides**
- A catalogue of visual themes and design materials.
- Page creation based on the actual purpose of the product.
- Redesign and audit workflows.
- Browser-based inspection of a URL, development server, or application.
- Design quality gates covering accessibility, responsive behaviour, and common visual anti-patterns.

**Why use it:** Useful for building or redesigning complete web pages where visual identity, content hierarchy, and the user's primary action should drive the layout.

**Example usage**
```text
/hallmark redesign <path>
/hallmark audit <path>
```

**Integration note:** Follow the repository's current installation instructions for Claude Code. The project also supports other coding-agent environments.

### 2.3 [Anatomy](https://github.com/wheresryan22/anatomy)

**Purpose:** A skill that explains technical concepts by constructing a real, interactive visual object that represents how the concept works.

**What it provides**
- Detailed isometric illustrations assembled from many precise parts.
- Interactive SVG, WebGL, and 3D visualizations.
- Live readouts and animations that connect the visual model to the underlying concept.
- Visual explanations for topics such as caches, rate limiters, and shared resources.

**Why use it:** Useful for technical education, onboarding, architecture explanations, and documentation where a static diagram would not communicate the behaviour of a system adequately.

**Installation**
```bash
npx skills add wheresryan22/anatomy -g
```

Example:
```text
/anatomy explain how a token bucket rate limiter works, interactive
```

---

## 3. Documentation and Knowledge Representation

### 3.1 [Diagram Design](https://github.com/cathrynlavery/diagram-design)

**Purpose:** An agent skill for producing polished, brand-aware diagrams as self-contained HTML and SVG files.

**What it provides**
- A broad library of diagram types, including architecture, sequence, flow, and comparison diagrams.
- Diagram styling aligned with a project's brand palette and typography.
- Import workflows for formats such as Mermaid, draw.io, Excalidraw, and PlantUML.
- Export to PNG and SVG.

**Why use it:** Useful for technical documentation, architecture descriptions, onboarding material, and presentations where diagrams need to be readable and visually consistent.

**Installation through Agent Skills**
```bash
npx skills add cathrynlavery/diagram-design
```

Claude Code marketplace installation:
```text
/plugin marketplace add cathrynlavery/diagram-design
/plugin install diagram-design@diagram-design
```

### 3.2 [Graphify](https://github.com/Graphify-Labs/graphify)

**Purpose:** A codebase and knowledge-graph tool that gives coding agents a structured view of relationships across a project.

**What it provides**
- Cross-file relationships such as calls, imports, inheritance, and mixins.
- Graph-based exploration of concepts, subsystems, and dependencies.
- Query, path-tracing, and explanation workflows over the generated graph.
- Support for code and additional knowledge sources such as documentation and media.
- Local code parsing using tree-sitter; optional semantic processing can use a configured backend.

**Why use it:** Useful for navigating large repositories, understanding dependencies, tracing execution paths, and giving an agent more structured project context than a collection of disconnected files.

**Installation**
```bash
uv tool install graphifyy
graphify install
```

Then use:
```text
/graphify .
```

For a project-scoped installation:
```bash
graphify install --project
```

**Important:** The official PyPI package is `graphifyy` (with two `y` characters); the command-line executable is `graphify`.

### 3.3 [Microsoft MarkItDown](https://github.com/microsoft/markitdown)

**Purpose:** A Python utility and command-line tool for converting files into Markdown, making their content easier to inspect, search, and process with LLMs.

**What it provides**
- Conversion support for formats including PDF, Word, PowerPoint, Excel, and other common document types.
- A command-line interface and Python API.
- Optional format-specific dependencies and third-party plugins.

**Why use it:** Useful in documentation and agent pipelines that need to ingest existing documents as Markdown. It can prepare source material for analysis, summarization, retrieval, or inclusion in a documentation workflow.

**Installation**
```bash
pip install 'markitdown[all]'
```

Example:
```bash
markitdown input.pdf -o output.md
```

**Integration note:** MarkItDown is not a Claude Code skill or plugin. It is a standalone conversion tool that Claude Code can invoke through terminal commands or a project workflow.

---

## 4. Interview Preparation

These two repositories are learning resources, not installable Claude Code plugins. They can nevertheless serve as reference material when preparing for technical interviews.

### 4.1 [Coding Interview University](https://github.com/jwasham/coding-interview-university)

**Purpose:** A structured self-study curriculum for computer science fundamentals and software engineering interviews.

**Main topics**
- Big-O notation and algorithmic complexity.
- Data structures: arrays, linked lists, stacks, queues, hash tables, trees, and graphs.
- Sorting, searching, recursion, and dynamic programming.
- Operating systems, processes, threads, networking, databases, and related fundamentals.
- Coding practice and interview preparation.

**Why use it:** A broad study roadmap for strengthening computer science fundamentals and preparing for algorithm-focused interviews.

### 4.2 [System Design Primer](https://github.com/donnemartin/system-design-primer)

**Purpose:** An organized guide to designing scalable systems and preparing for system design interviews.

**Main topics**
- Scalability, latency, throughput, availability, and consistency.
- Load balancing, caching, CDNs, and distributed-system patterns.
- Databases, replication, sharding, and data partitioning.
- Architecture trade-offs and common large-scale system components.
- System design and object-oriented design interview questions with sample solutions.
- Anki flashcards for spaced-repetition study.

**Why use it:** A core reference for learning system architecture and practising the trade-off analysis expected in system design interviews.

---

## 5. Suggested Usage by Workflow

| Workflow stage | Recommended resources | Intended outcome |
|---|---|---|
| Clarify requirements | Matt Pocock Skills | Reduce ambiguity before implementation |
| Set engineering constraints | Karpathy-inspired Guidelines | Encourage simplicity and scoped changes |
| Plan and execute a larger feature | Superpowers | Follow a structured specification, plan, TDD, and review process |
| Implement efficiently | Ponytail | Reuse existing code and avoid unnecessary complexity |
| Extend the agent environment | ECC | Add selected agents, skills, hooks, and automation |
| Build or refine a UI | Impeccable, Hallmark | Improve visual direction and design quality |
| Explain a technical concept visually | Anatomy | Produce interactive visual explanations |
| Create architecture or process diagrams | Diagram Design | Generate consistent, reusable diagrams |
| Understand a large codebase | Graphify | Explore code relationships and project structure |
| Ingest existing documents | MarkItDown | Convert source documents into Markdown |
| Prepare for coding interviews | Coding Interview University | Study CS fundamentals and algorithms |
| Prepare for architecture interviews | System Design Primer | Practise scalable-system design and trade-offs |

## 6. Installation and Governance Recommendations

1. **Do not install everything indiscriminately.** Start with the resources relevant to the current project and workflow.
2. **Avoid overlapping instruction systems.** Matt Pocock, Ponytail, Superpowers, ECC, and the Karpathy-inspired guidelines can influence similar engineering behaviours. Review their instructions and decide which should take precedence.
3. **Inspect hooks and scripts.** Before enabling any plugin or toolkit, review its hooks, shell commands, permissions, network access, and file modifications.
4. **Prefer project-scoped installation where appropriate.** This makes the toolchain explicit, reviewable, and easier to reproduce across machines.
5. **Keep learning resources separate from runtime plugins.** Coding Interview University and System Design Primer are references; MarkItDown is a conversion utility. They do not need to be installed as Claude Code skills.
6. **Verify installation instructions against the source repository.** Commands and supported agent platforms can change; use each project's README and release notes as the authoritative source.

## Sources

All descriptions and installation examples above are based on the repositories' public documentation. Consult the source repositories for current versions, licensing, complete feature lists, and installation requirements.

- https://github.com/mattpocock/skills
- https://github.com/DietrichGebert/ponytail
- https://github.com/obra/superpowers
- https://github.com/affaan-m/ECC
- https://github.com/multica-ai/andrej-karpathy-skills
- https://github.com/pbakaus/impeccable
- https://github.com/Nutlope/hallmark
- https://github.com/wheresryan22/anatomy
- https://github.com/cathrynlavery/diagram-design
- https://github.com/Graphify-Labs/graphify
- https://github.com/microsoft/markitdown
- https://github.com/jwasham/coding-interview-university
- https://github.com/donnemartin/system-design-primer
