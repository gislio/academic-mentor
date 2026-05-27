# Academic Agents: Distribution Package

This is the distribution package for the **Academic Agents framework**, a system of eleven Claude agents that support academic research and writing across the full arc of a project, from problem framing through publication and viva preparation. The framework is grounded in a 212-source corpus of canonical research-methods and academic-writing literature, and every substantive claim the agents produce is cited in APA7 form to a specific source in that corpus.

This README is the comprehensive guide to the framework. Read the **Overview** for what the framework is and why. Read **How the Framework Works** for the architecture. Read **Installation** for how to get the framework into your Claude project. Read **Using the Agents** for the per-agent reference, including triggers, what each agent reads, what it produces, and worked examples.

---

## Table of Contents

1. Overview
2. How the Framework Works
3. Citation Discipline
4. The Knowledge Base
5. Installation
6. Using the Agents
7. Working with User-Supplied Papers
8. Workflows for Common Tasks
9. Troubleshooting and FAQs
10. Files in This Distribution
11. License and Attribution

---

## 1. Overview

### What the Framework Is

Academic Agents is a collection of eleven Claude agents designed to support academic researchers and writers at every stage of an empirical research project, calibrated for doctoral, master's, journal-article, and undergraduate final-year work. The agents draw on a knowledge base of 35 topic files synthesized from 212 canonical sources in research methods, academic writing, peer review, publication, and citation discipline.

### What the Framework Does

The framework helps users perform the tasks academic work requires: choosing a research philosophy and approach, drafting and critiquing problem statements and research proposals, conducting literature reviews and systematic reviews, building conceptual and theoretical frameworks, designing quantitative, qualitative, and mixed-methods studies, planning sampling and data collection, executing analysis, addressing ethics, defending reliability and validity, structuring a thesis or dissertation, drafting and critiquing every chapter from introduction to conclusion, matching manuscripts to journals, drafting cover letters and response-to-reviewers documents, drafting statistical interpretation paragraphs in multiple registers, applying APA7 citation discipline, verifying reference lists, performing background synthesis of user-supplied papers with strict citation verification, stress-testing arguments, checking claims against canonical sources, and applying philosophy-of-science critique.

### Why a Framework Rather Than a Single Agent

A single agent would have to hold every academic-methods convention, every writing convention, every citation rule, and every critique discipline simultaneously, with the resulting risk that no one part is held well. The framework distributes the work across specialized agents, each grounded in a focused subset of the knowledge base. The user invokes the agent that matches the current task; the agents hand off to one another when the work crosses cluster boundaries.

### Who the Framework Is For

- **Doctoral candidates** working through a dissertation from proposal to viva.
- **Master's students** producing a dissertation under tighter time and scope constraints.
- **Journal-article authors** at any career stage preparing a manuscript for peer review.
- **Postdocs and faculty** who want methodological support, journal-matching help, peer-review-response drafting, or critique of work in progress.
- **Undergraduate final-year thesis writers** at programs where dissertation work begins early.

The framework is **discipline-agnostic by default**. It defaults to general academic best practice and surfaces field-specific guidance (education, social sciences, health, linguistics, legal, business, and others where the corpus is rich) when the user signals their discipline.

---

## 2. How the Framework Works

### The Eleven Agents

The framework has three tiers: an orchestrator at the top, seven specialists in the middle, and three utility agents at the bottom. Every agent and command is prefixed `academic-`.

**The orchestrator** (`academic-mentor`) routes a general request to the right specialist after a small number of clarifying questions. It is optional; users who know which specialist they need can call it directly.

**The seven specialists** cover the substantive academic work, each grounded in one cluster of the knowledge base:

- `academic-research-foundations-advisor` — research philosophy, research approach, problem statement and research questions, research proposal.
- `academic-literature-work-advisor` — literature review, systematic and scoping reviews, conceptual framework, theoretical framework, background synthesis.
- `academic-methods-advisor` — quantitative, qualitative, and mixed methods, sampling, data collection, data analysis, ethics, reliability and validity.
- `academic-writing-and-structure-advisor` — thesis or dissertation structure, every chapter from introduction through conclusion, academic writing style.
- `academic-publication-craft-advisor` — journal matching, manuscript submission and peer-review response, statistical interpretation drafts, storytelling and argument craft.
- `academic-critique-advisor` — argument stress-testing, claim-checking against canonical sources, philosophy-of-science critique, configurable in constructive or examiner mode.
- `academic-citation-and-integrity-advisor` — APA7, reference verification, paraphrase audit, plagiarism risk.

**The three utility agents** are called by specialists (or directly by the user) for narrow, high-precision tasks:

- `academic-source-retriever` — fetches verbatim passages from the corpus with full APA7 citation.
- `academic-apa7-formatter` — mechanically formats and converts citation styles.
- `academic-background-synthesizer` — produces structured syntheses from user-supplied papers, closed-corpus by default.

### How Agents Hand Off

Each agent's specification names the other agents it hands off to and the conditions under which the handoff occurs. A typical engagement may move through several agents. For example, a doctoral candidate writing up their thesis might begin with `academic-writing-and-structure-advisor` for the discussion chapter, hand to `academic-critique-advisor` for a stress-test of the argument, hand to `academic-citation-and-integrity-advisor` for the reference-list audit, and finally invoke `academic-publication-craft-advisor` when the thesis becomes a journal article. The agents are designed so handoffs are explicit and the user remains oriented.

### Tone Across the System

Every agent operates in a calm, thoughtful, reflective tone. The `academic-critique-advisor` is the exception: it offers an **examiner mode** that is rigorous and direct, simulating the toughest viva or peer-review experience. Even in examiner mode the agent never ridicules; it presses on the work, not the person.

### When the Framework Pauses

The agents are designed to pause for the user's input at decision points rather than to produce long output speculatively. They ask clarifying questions before substantive work begins, confirm direction before producing output, and surface options when more than one defensible path exists. This matches the project's design principle that the user remains the author and the agents support rather than replace.

---

## 3. Citation Discipline

This is the framework's load-bearing commitment.

### The Rule

No agent asserts a substantive framework, procedure, decision criterion, or empirical claim without citing a source. Every substantive claim drawn from the knowledge base carries an APA7 in-text citation followed by the internal source ID in square brackets, for example "(Cohen et al., 2018) [S161]". Claims drawn from user-supplied papers carry "[user-supplied]" in addition to the APA7 citation.

### What This Means in Practice

The agents will not assert, for example, that a literature review must follow a six-step process without naming the source for that claim (Machi & McEvoy, 2022). They will not assert that hypotheses must be falsifiable without citing the canonical source for that requirement (Sekaran & Bougie, 2017, citing Popper). They will not assert that a particular paradigm carries particular commitments without grounding the claim in a methodological handbook.

This discipline produces output the user can defend. Every claim in a draft chapter, every framework in a methodology section, every recommendation in a discussion section, is traceable to a source the user can consult, verify, and cite in their own document.

### What Happens When the Agent Cannot Cite a Claim

The agent flags the gap rather than producing an unsupported claim. If the user is working on a topic the corpus is thin on (the corpus skews toward education, social sciences, health, and business, and is thinner on, for example, pure philosophy of science or experimental natural sciences), the agent will say so and offer to work from user-supplied sources instead.

### Citation Style

APA7 is the framework's default style, in line with the project's instructions. The `academic-citation-and-integrity-advisor` and the `academic-apa7-formatter` utility can convert from or to other styles when a journal or institution requires a different convention.

---

## 4. The Knowledge Base

### What Is in the Knowledge Base

The knowledge base contains:

- **35 topic files** in `Knowledge Base/topics/`, each in a ten-section template (When to Use; Overview; Core Frameworks; Procedural Guidance; Decision Criteria; Worked Example; Common Pitfalls; Disagreements in the Corpus; Connections to Other Topics; Sources Cited). Each file covers one academic-research topic, cites canonical sources in APA7 with internal source IDs, and ends with a reference list.

- **The master source index** at `Knowledge Base/sources/sources_index.md`, with the APA7 reference, the in-text citation form, and the internal source ID for each of the 212 sources in the corpus. The corresponding machine-readable file is `Knowledge Base/_meta/sources_index.json`.

- **The topics catalog** at `Knowledge Base/indexes/topics_index.md`, with a one-sentence "when to use this topic" pointer for each of the 35 files.

- **The architecture proposal** at `Knowledge Base/_meta/agent_architecture_proposal.md`, which describes the framework's design.

### The 212-Source Corpus

The full corpus of 212 academic-writing and research-methods sources lives in `Background Material/` at the project root. The agents reference the corpus by internal source ID rather than reading the source files directly, except for the `academic-source-retriever` utility, which fetches verbatim passages on request. If the `Background Material/` folder is not accessible at runtime, the agents will still produce citations to the corpus but cannot retrieve passages from it.

### What Is Not in the Knowledge Base

The knowledge base does not contain user-supplied papers. When the user provides papers at runtime (typically to the `academic-background-synthesizer`, `academic-critique-advisor`, or `academic-literature-work-advisor`), the agents treat those papers as authoritative within their scope and cite them with "[user-supplied]" alongside the APA7 citation.

---

## 5. Installation

### Option A: Install the Plugin (Recommended)

The simplest installation is the `academic-agents.plugin` file in this DIST folder. Installing it adds all eleven agents and the shared reference pool to your Claude environment at once.

To install: open Claude, present the `academic-agents.plugin` file, and click the install button when it appears. The agents become available as both skills (auto-triggered when the user types phrases the agents listen for) and slash commands (typeable as `/academic-mentor`, `/academic-research-foundations-advisor`, and so on for each agent).

### Option B: Install Individual Skills

Each agent is also packaged as an individual `.skill` file in `DIST/skills/`. Install only the agents you want by presenting the corresponding `.skill` files one at a time. Useful for users who only need a subset (for example, a journal-article author who only wants `academic-publication-craft-advisor` and `academic-citation-and-integrity-advisor`).

### Option C: Use the Source Files Directly

The agent specifications in `Agents/` and the knowledge base in `Knowledge Base/` can be used directly without any plugin installation. Open the Claude project and ask any agent question; Claude will read the relevant files as needed. This mode is useful for development, customization, and inspecting how the framework is built.

### What Each Installation Gives You

Whichever installation method you choose, you get:

- The ability to invoke any of the eleven agents by name in conversation.
- The ability to invoke any agent through its slash command.
- Access to the full 35-file knowledge base, with strict APA7 citation discipline.
- The `academic-mentor` orchestrator that can route requests when the user is not sure which agent to use.

---

## 6. Using the Agents

This section is the per-agent reference. For each agent, it names the triggers, the topics it reads, what it produces, and a worked example.

### 6.1 `academic-mentor` (orchestrator)

**Trigger.** Invoke when you want to be routed to the right specialist and you are not sure which one to use. Example prompts include "I am writing a thesis and need help," "I do not know where to start," "I am preparing for my viva," and similar general statements.

**Reads.** The topics catalog and the agent architecture proposal. The orchestrator does not produce substantive output; it routes.

**Produces.** A short confirmation of what you said, a routing recommendation, and an invitation to confirm.

**Slash command.** `/academic-mentor`.

**Worked example.** *You*: "I am at the proposal stage of my doctoral dissertation and feeling lost." *academic-mentor*: "I will route you to `academic-research-foundations-advisor`, which covers research philosophy, approach, problem statement, and the proposal as a whole. Before I do, four quick questions: What level (doctoral / master's / other)? What discipline? What stage are you specifically at (problem framing, methodology design, full proposal draft)? What would you like the next step to produce?" Once you answer, the orchestrator hands off.

### 6.2 `academic-research-foundations-advisor`

**Trigger.** Research philosophy, research approach (deductive, inductive, abductive, mixed), problem statement and research questions, the proposal as a whole. Examples: "help me articulate my research philosophy," "critique my problem statement," "draft Chapter 1 of my proposal," "what philosophy is implicit in my proposal."

**Reads.** Four topic files: `research_philosophy.md`, `research_approach.md`, `problem_statement_and_questions.md`, `research_proposal.md`. Plus the master source index.

**Produces.** Drafted or critiqued sections: problem statements, research-philosophy sections defending a paradigm, research-approach sections justifying a logic of inquiry, proposal chapters (typically Chapter 1, 2, or 3 of a five-chapter model).

**Slash command.** `/academic-research-foundations-advisor`.

**Worked example.** *You*: "Help me articulate my research philosophy for a study on remote-work practices in knowledge teams." *Agent*: "Before I begin, a few questions: What does your field expect as the default paradigm? Have you provisionally chosen one? What is the question's logical shape?" After answering, the agent walks through the corpus's four-paradigm scheme (Sekaran & Bougie, 2017 [S147]) and helps you locate yourself, citing the relevant sources at every step.

### 6.3 `academic-literature-work-advisor`

**Trigger.** Literature reviews of all types, systematic and scoping reviews, conceptual or theoretical frameworks, background synthesis. Examples: "structure my literature review chapter," "design a systematic review protocol," "build a conceptual framework," "synthesize these ten background papers."

**Reads.** Four topic files: `literature_review.md`, `systematic_and_scoping_reviews.md`, `conceptual_framework.md`, `theoretical_framework.md`. Plus the master source index.

**Produces.** Literature-review chapters or sections; systematic-review protocols; conceptual-framework diagrams and explanations; theoretical-framework chapters; background syntheses (delegated to the `academic-background-synthesizer` utility).

**Slash command.** `/academic-literature-work-advisor`.

**Worked example.** *You*: "Help me design a systematic review of interventions for teacher burnout in elementary schools." *Agent*: "I will walk you through the SALSA framework (Booth et al., 2021 [S180]). First questions: What is the specific research question? Do you have access to multiple databases? Is this for PROSPERO registration?" The agent then walks through the eight steps of the canonical systematic-review procedure, citing PRISMA 2020, GRADE, AMSTAR2, and the other relevant standards from the knowledge base.

### 6.4 `academic-methods-advisor`

**Trigger.** Choosing or critiquing methods (quantitative, qualitative, mixed), sampling, data collection, data analysis, ethics, reliability and validity. Examples: "help me choose a research method," "design a sampling plan," "draft my interview protocol," "defend the validity of my study."

**Reads.** Eight topic files (all of Cluster 3): `quantitative_methods.md`, `qualitative_methods.md`, `mixed_methods.md`, `sampling_techniques.md`, `data_collection_methods.md`, `data_analysis_procedures.md`, `ethical_considerations.md`, `reliability_and_validity.md`. Plus the master source index.

**Produces.** Drafted methodology sections, sampling plans, data-collection protocols, analysis plans, ethics sections, reliability-and-validity defenses, methodology-chapter critiques.

**Slash command.** `/academic-methods-advisor`.

**Worked example.** *You*: "I want to study how nurses experience moral distress in palliative care. What method should I use?" *Agent*: "I will help you choose. Tell me: What is the logical shape of your question? Causal, descriptive, sense-making? What evidence base will answer it? What constraints (timeline, access, ethics)?" The agent walks through the corpus's decision criteria, recommending a qualitative approach with phenomenological or case-study elements (Tracy, 2020 [S130]), and helps you design the sampling, data collection, and analysis.

### 6.5 `academic-writing-and-structure-advisor`

**Trigger.** Any writing task in a thesis, dissertation, or article. Examples: "structure my thesis," "draft my background section," "improve my findings chapter," "draft a contribution statement for my viva," "polish my prose."

**Reads.** Ten topic files (all of Cluster 4): `thesis_and_dissertation_structure.md`, `background_and_context.md`, `scope_and_limitations.md`, `presentation_of_findings.md`, `interpretation_of_results.md`, `comparison_with_literature.md`, `theoretical_and_practical_implications.md`, `conclusion_and_contribution_to_knowledge.md`, `suggestions_for_future_research.md`, `academic_writing_style.md`. Plus the master source index.

**Produces.** Drafted or revised chapters or sections, prose-craft critiques, structural diagnoses, viva-preparation contribution statements.

**Slash command.** `/academic-writing-and-structure-advisor`.

**Worked example.** *You*: "Critique my discussion chapter. It feels weak but I cannot pinpoint why." *Agent*: "Let me read it. Before I do: What are your three to five main findings? What is your conceptual or theoretical framework? What did you mean the chapter to argue?" The agent then reads the chapter against the corpus's standards (Terrell, 2022 [S210]; Roberts & Hyatt, 2024 [S193]), identifies the structural and prose-level weaknesses, and proposes specific revisions with rationales.

### 6.6 `academic-publication-craft-advisor`

**Trigger.** Journal matching, manuscript submission, peer-review response, statistical interpretation drafts, storytelling craft. Examples: "find five candidate journals for this abstract," "draft a cover letter," "help me respond to these reviewer comments," "draft three versions of this statistical paragraph."

**Reads.** Four topic files: `journal_matching.md`, `manuscript_submission_and_peer_review.md`, `statistical_interpretation_drafts.md`, `storytelling_and_argument_craft.md`. Plus the master source index.

**Produces.** Ranked candidate-journal lists with rationale; cover letters; response-to-reviewers documents; statistical-interpretation paragraphs in formal-technical, applied, and narrative registers; storytelling-revised chapters.

**Slash command.** `/academic-publication-craft-advisor`.

**Worked example.** *You*: "Here is my abstract on remote-work-and-trust in distributed teams. Find five candidate journals." *Agent*: "I will apply the multi-source approach (Becker & Denicolo, 2012 [S117]). A few questions: What is your career stage? What audience matters most for your contribution? Are there time constraints?" The agent then produces a ranked list of five candidate journals with a one-or-two-sentence rationale per journal addressing aims and scope, audience, methodological tradition, impact factor, and time to decision.

### 6.7 `academic-critique-advisor`

**Trigger.** When you want your work tested rather than supported. Examples: "find where my argument falls apart," "compare my draft against these canonical papers," "what would a philosopher of science say is missing," "simulate a hostile examiner."

**Reads.** Three topic files: `argument_stress_testing.md`, `claim_checking_against_canonical_sources.md`, `philosophy_of_science_critique.md`. Plus relevant Cluster 1 to 5 files when the critique requires understanding the upstream choices. Plus user-supplied canonical papers.

**Produces.** Structured weakness lists organized by severity; rehearsed responses to objections; coverage reports showing which tests were applied.

**Modes.** Constructive (default) and examiner. Tell the agent which mode you want.

**Slash command.** `/academic-critique-advisor`.

**Worked example.** *You*: "I have a draft of my discussion chapter and the five most important papers in my field. Tell me where my argument contradicts or oversimplifies what these authors actually found." *Agent*: "I will apply the claim-checking discipline (Machi & McEvoy, 2022 [S194]; Wette, 2021 [S204b]). Are the five papers attached? Which is your preferred mode: constructive or examiner?" The agent then works through the load-bearing citations in your draft, compares each against the canonical paper it leans on, and surfaces contradictions, oversimplifications, and misattributions with specific corrections.

### 6.8 `academic-citation-and-integrity-advisor`

**Trigger.** Any citation or referencing task. Examples: "format these references in APA7," "verify my reference list," "check this paraphrase for plagiarism risk," "audit my in-text citations."

**Reads.** Two topic files: `citation_and_referencing.md`, `source_verification.md`. Plus the master source index.

**Produces.** Corrected reference lists; error reports with corrections; in-text-to-reference-list cross-check reports; paraphrase audits; converted reference lists.

**Slash command.** `/academic-citation-and-integrity-advisor`.

**Worked example.** *You*: "Drop in my bibliography. Flag anything that does not match its DOI, page number, or year." *Agent*: "I will apply the four-field verification (Pears & Shields, 2025 [S024]). Should I resolve every DOI and report failures? Should I fix unambiguous errors automatically or flag them for you to fix?" The agent then runs the verification and produces a list of errors with proposed corrections, separating fixable ones from those that require your judgment.

### 6.9 `academic-source-retriever` (utility)

**Trigger.** When a specific passage from the 212-source corpus is needed. Most often called by another agent; users can call directly with "what does Source X say about Topic Y?"

**Reads.** The master source index. Then the specific source file in `Background Material/` once identified.

**Produces.** Verbatim passages with full APA7 citation, internal source ID, and section heading or line range.

**Slash command.** `/academic-source-retriever`.

### 6.10 `academic-apa7-formatter` (utility)

**Trigger.** Mechanical formatting tasks. Examples: "format these references in APA7," "convert this list from MLA to APA7," "standardize author names."

**Reads.** `citation_and_referencing.md` and `source_verification.md`.

**Produces.** Formatted reference lists, converted lists, lists of annotated changes.

**Slash command.** `/academic-apa7-formatter`.

### 6.11 `academic-background-synthesizer` (utility)

**Trigger.** When you have a set of background papers and want a structured synthesis. Examples: "here are ten papers; synthesize them with verified citations," "produce a background-context section from these uploads."

**Reads.** The user-supplied papers (mandatory). Plus `literature_review.md`, `citation_and_referencing.md`, `source_verification.md`. The knowledge base's substantive content is NOT drawn on by default; the user can opt in.

**Produces.** Structured prose synthesis grounded entirely in the user-supplied papers; APA7 reference list of those papers; gap-flagging notes.

**Slash command.** `/academic-background-synthesizer`.

**Default mode.** Closed corpus. The agent uses only the papers you provide. You can opt in to add knowledge-base material with explicit marking.

---

## 7. Working with User-Supplied Papers

Three of the agents work directly with papers you provide at runtime: the `academic-critique-advisor` (for claim-checking against canonical sources), the `academic-background-synthesizer` (for syntheses you provide papers for), and the `academic-literature-work-advisor` (which delegates synthesis tasks to the synthesizer).

### How to Provide Papers

Either attach the papers to the conversation directly, or place them in a project folder and tell the agent the path. The agents accept PDF, Word, plain text, or markdown.

### What the Agents Do with Them

The agents read the papers, identify the relevant passages, and ground their output in those passages. They cite each substantive claim with the paper's full APA7 citation and "[user-supplied]" to mark the source pool. Page numbers are included where the user has provided them or where the paper's structure makes them identifiable.

### What the Agents Will Not Do

The agents will not assert claims the user-supplied papers do not support. If the user asks for a synthesis that includes material the papers do not cover, the agent flags the gap rather than fill it. For `academic-background-synthesizer` specifically, the default closed-corpus mode means the agent will refuse to add knowledge-base material unless the user explicitly opts in.

---

## 8. Workflows for Common Tasks

### Workflow A: Starting a Doctoral Proposal

1. Call `academic-mentor` or directly `academic-research-foundations-advisor`.
2. Work through the four routing questions.
3. Draft the problem statement and research questions iteratively with the agent.
4. Move to research philosophy and approach.
5. Hand off to `academic-literature-work-advisor` when ready to draft the literature review chapter.
6. Hand off to `academic-methods-advisor` when ready to draft the methodology chapter.
7. Return to `academic-research-foundations-advisor` to assemble the proposal.
8. Call `academic-critique-advisor` for a stress-test before submission to the committee.
9. Call `academic-citation-and-integrity-advisor` for a reference-list audit.

### Workflow B: Writing a Discussion Chapter

1. Call `academic-writing-and-structure-advisor`.
2. Share your findings chapter (Chapter 4) and your draft discussion (Chapter 5, if any).
3. Work through interpretation, comparison with literature, implications, conclusion, and future research in turn, drafting each section.
4. Call `academic-critique-advisor` to stress-test the argument.
5. Call `academic-citation-and-integrity-advisor` for the citation audit.

### Workflow C: Submitting a Journal Article

1. Call `academic-publication-craft-advisor`.
2. Provide your abstract.
3. Receive a ranked list of five or more candidate journals.
4. Confirm your target and draft the cover letter.
5. After submission and reviewer decision, return to the agent to draft the response-to-reviewers document.
6. Call `academic-citation-and-integrity-advisor` for any reference-list work the submission requires.

### Workflow D: Preparing for a Viva

1. Call `academic-critique-advisor` in **examiner mode**.
2. Provide your dissertation (or its key chapters).
3. Receive rehearsed objections from multiple paradigm perspectives.
4. Draft and refine your responses to each.
5. Optional: Return to `academic-writing-and-structure-advisor` to refine the one-sentence contribution statement you will deliver at the start of the viva.

### Workflow E: Background Synthesis from User-Supplied Papers

1. Call `academic-background-synthesizer` (or `academic-literature-work-advisor`, which delegates).
2. Provide the papers (typically 5 to 20 for a synthesis chapter section).
3. Confirm closed-corpus mode (default) or opt into knowledge-base integration.
4. Receive a structured synthesis with every claim cited to a specific paper.

### Workflow F: Reference-List Audit

1. Call `academic-citation-and-integrity-advisor`.
2. Provide your reference list.
3. Receive a list of errors and corrections, separated into unambiguous fixes and entries requiring your judgment.

---

## 9. Troubleshooting and FAQs

### Why does the agent refuse to assert a claim?

Because the framework's citation discipline requires every substantive claim to be traceable to a source. If the corpus does not contain a source for the claim and the user has not provided one, the agent flags the gap rather than asserting an uncited claim. This is a feature.

### The corpus is thin on my discipline. What do I do?

Supply the agents with the papers from your discipline directly. The `academic-background-synthesizer` and the `academic-critique-advisor` work specifically with user-supplied papers. The other specialists will still draw on the corpus for general academic conventions (writing style, citation discipline, proposal structure) while citing your papers for discipline-specific content.

### Can I use a citation style other than APA7?

Yes. The `academic-apa7-formatter` utility can convert between styles. Tell any specialist agent the style your institution or journal requires, and it will adjust its output.

### How do I know which specialist to call?

Either call `academic-mentor` and let it route you, or read the trigger lists in the per-agent reference above (Section 6).

### Can I install only some of the agents?

Yes. Each `.skill` file in `DIST/skills/` is installable individually. Pick the ones you need.

### Does the framework work without internet access?

The framework's content is local: the topic files, the source index, and the agent specifications all live in the project folder. The agents work offline. Web search is only used if the agent explicitly invokes it (none of the specialists do by default).

### Can the framework be customized?

Yes. The topic files are markdown and can be edited; new sources can be added to the index; new agents can be created in the same format. The framework is designed to be extensible.

### What level of academic work does the framework target?

All four levels listed in the project brief: doctoral, master's, journal-article, and undergraduate final-year. The agents calibrate depth and convention to the level the user names in routing.

---

## 10. Files in This Distribution

### Top-Level

- `README.md` — this document.
- `academic-agents.plugin` — the full plugin, recommended installation.

### Skills

In `DIST/skills/`:

- `academic-mentor.skill`
- `academic-research-foundations-advisor.skill`
- `academic-literature-work-advisor.skill`
- `academic-methods-advisor.skill`
- `academic-writing-and-structure-advisor.skill`
- `academic-publication-craft-advisor.skill`
- `academic-critique-advisor.skill`
- `academic-citation-and-integrity-advisor.skill`
- `academic-source-retriever.skill`
- `academic-apa7-formatter.skill`
- `academic-background-synthesizer.skill`

Each `.skill` is a self-contained zip archive of a skill directory. Each contains SKILL.md, the topic files relevant to that agent, the master source index, and the slash command file.

### Each Skill's Internal Structure

```
academic-X-advisor/
├── SKILL.md
├── reference/
│   ├── (relevant topic files)
│   └── sources_index.md
└── commands/
    └── academic-X-advisor.md
```

### Plugin's Internal Structure

```
academic-agents.plugin/
├── manifest.json
├── README.md
├── skills/
│   └── (all 11 skill directories)
├── shared/
│   ├── topics/ (all 35 topic files)
│   ├── sources/ (full source index)
│   ├── indexes/ (topics catalog)
│   └── _meta/ (architecture proposal)
└── commands/
    └── (slash commands for all 11 agents)
```

---

## 11. License and Attribution

### The Framework

The agent specifications and the topic files are original synthesis produced by the project author for use in this Claude project. They may be customized, extended, or redistributed in line with the project owner's preferences.

### The Background Corpus

The 212 sources in `Background Material/` are the property of their respective authors and publishers. The framework cites them in APA7 form throughout; redistribution of the source files themselves is governed by their original copyright. The framework's `Knowledge Base/sources/sources_index.md` and the topic files cite the corpus rather than reproducing it.

### Citation of the Framework Itself

If you use the framework in your academic work and find it helpful to acknowledge, you can cite it as:

> Academic Agents framework (2026). Eleven-agent system for academic research and writing support, grounded in a 212-source corpus of canonical research-methods and academic-writing literature. Built in a Claude project.

---

*End of README.*
