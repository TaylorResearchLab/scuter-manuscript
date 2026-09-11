---
title: 'SCUTER: A User-Directed Framework for Reproducible Scientific Collaboration Across AI Systems'
keywords:
- artificial intelligence
- scientific collaboration
- human-AI collaboration
- reproducibility
- provenance
- FAIR
- Manubot
lang: en-US
date-meta: '2026-09-11'
author-meta:
- Deanne M. Taylor
header-includes: |
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta property="og:type" content="article" />
  <meta name="dc.title" content="SCUTER: A User-Directed Framework for Reproducible Scientific Collaboration Across AI Systems" />
  <meta name="citation_title" content="SCUTER: A User-Directed Framework for Reproducible Scientific Collaboration Across AI Systems" />
  <meta property="og:title" content="SCUTER: A User-Directed Framework for Reproducible Scientific Collaboration Across AI Systems" />
  <meta property="twitter:title" content="SCUTER: A User-Directed Framework for Reproducible Scientific Collaboration Across AI Systems" />
  <meta name="dc.date" content="2026-09-11" />
  <meta name="citation_publication_date" content="2026-09-11" />
  <meta property="article:published_time" content="2026-09-11" />
  <meta name="dc.modified" content="2026-09-11T11:22:47+00:00" />
  <meta property="article:modified_time" content="2026-09-11T11:22:47+00:00" />
  <meta name="dc.language" content="en-US" />
  <meta name="citation_language" content="en-US" />
  <meta name="dc.relation.ispartof" content="Manubot" />
  <meta name="dc.publisher" content="Manubot" />
  <meta name="citation_journal_title" content="Manubot" />
  <meta name="citation_technical_report_institution" content="Manubot" />
  <meta name="citation_author" content="Deanne M. Taylor" />
  <meta name="citation_author_institution" content="Department of Biomedical and Health Informatics, Children&#39;s Hospital of Philadelphia, Philadelphia, Pennsylvania, USA" />
  <meta name="citation_author_institution" content="Department of Pediatrics, Perelman School of Medicine, University of Pennsylvania, Philadelphia, Pennsylvania, USA" />
  <link rel="canonical" href="https://TaylorResearchLab.github.io/scuter-manuscript/" />
  <meta property="og:url" content="https://TaylorResearchLab.github.io/scuter-manuscript/" />
  <meta property="twitter:url" content="https://TaylorResearchLab.github.io/scuter-manuscript/" />
  <meta name="citation_fulltext_html_url" content="https://TaylorResearchLab.github.io/scuter-manuscript/" />
  <meta name="citation_pdf_url" content="https://TaylorResearchLab.github.io/scuter-manuscript/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://TaylorResearchLab.github.io/scuter-manuscript/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://TaylorResearchLab.github.io/scuter-manuscript/v/0db5841a512e81851c695784f2bbd68ea3d7fc13/" />
  <meta name="manubot_html_url_versioned" content="https://TaylorResearchLab.github.io/scuter-manuscript/v/0db5841a512e81851c695784f2bbd68ea3d7fc13/" />
  <meta name="manubot_pdf_url_versioned" content="https://TaylorResearchLab.github.io/scuter-manuscript/v/0db5841a512e81851c695784f2bbd68ea3d7fc13/manuscript.pdf" />
  <meta property="og:type" content="article" />
  <meta property="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />
  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />
  <meta name="theme-color" content="#ad1457" />
  <!-- end Manubot generated metadata -->
bibliography:
- content/manual-references.json
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
manubot-clear-requests-cache: false
...






<small><em>
This manuscript
([permalink](https://TaylorResearchLab.github.io/scuter-manuscript/v/0db5841a512e81851c695784f2bbd68ea3d7fc13/))
was automatically generated
from [TaylorResearchLab/scuter-manuscript@0db5841](https://github.com/TaylorResearchLab/scuter-manuscript/tree/0db5841a512e81851c695784f2bbd68ea3d7fc13)
on September 11, 2026.
</em></small>



## Authors



+ **Deanne M. Taylor**
  ^[✉](#correspondence)^<br>
  <small>
     Department of Biomedical and Health Informatics, Children's Hospital of Philadelphia, Philadelphia, Pennsylvania, USA; Department of Pediatrics, Perelman School of Medicine, University of Pennsylvania, Philadelphia, Pennsylvania, USA
  </small>


::: {#correspondence}
✉ — Correspondence possible via [GitHub Issues](https://github.com/TaylorResearchLab/scuter-manuscript/issues)
or email to
Deanne M. Taylor \<taylordm@chop.edu\>.


:::


# Abstract


# Introduction

General-purpose artificial intelligence systems are increasingly being used as active participants in scientific work, including literature review, analysis, software development, interpretation, and writing. In a sustained research project, however, useful work rarely occurs within a single conversation. Scientific questions change as evidence accumulates, analyses are revised, files and code move through multiple versions, and different people or AI systems may contribute at different stages. When this work is distributed across chat sessions or AI platforms, important scientific context can become separated from the artifacts, evidence, and decisions that produced an accepted result. The practical challenge is therefore not only how to obtain useful output from an AI system, but how to preserve scientific continuity, provenance, review, and human control as the work develops.

These requirements have substantial precedent in established scientific practice. Reproducible computational research depends on retaining the information needed to reconstruct how a result was produced, including relevant code, inputs, parameters, software environments, and links between reported claims and their supporting evidence [@doi:10.1371/journal.pcbi.1003285]. Provenance frameworks similarly distinguish the entities, activities, and responsible participants involved in producing and transforming research objects [@url:https://www.w3.org/TR/2013/REC-prov-dm-20130430]. Electronic laboratory notebooks extend this principle to the organization and recovery of scientific records over time, while version-controlled publication workflows demonstrate how scientific artifacts, revisions, review, and citation information can remain connected during collaborative work [@doi:10.1038/s41596-021-00645-8; @doi:10.1186/s13321-017-0221-3; @doi:10.1371/journal.pcbi.1007128]. The FAIR principles provide a broader framework for making digital research objects findable, accessible, interoperable, and reusable through persistent identifiers, metadata, access mechanisms, and provenance [@doi:10.1038/sdata.2016.18]. Together, these traditions establish that a scientific record should preserve more than the final result: it should retain enough of the path to that result for later inspection and reuse.

Human participation in AI-assisted work also requires an explicit allocation of authority. Work on mixed-initiative systems has long emphasized that automated assistance must accommodate changing user goals, uncertainty, intervention, and termination rather than assuming that control should remain with the automated system [@doi:10.1145/302979.303030]. More recent work has similarly examined approval, escalation, and delegation as explicit components of human-AI interaction [@arxiv:2507.14034; @arxiv:2606.17099]. These concerns are particularly important in scientific research, where deciding whether evidence is sufficient, whether an assumption remains valid, or whether a result should redirect the project is part of the scientific process itself.

At the same time, multi-agent systems have shown that complex work can be coordinated through specialized roles, shared state, structured intermediate products, and explicit handoffs among participants [@doi:10.1145/356810.356816; @arxiv:2308.08155; @arxiv:2308.00352; @arxiv:2307.07924]. More recent systems have extended these ideas to scientific work, including literature synthesis, data analysis, experimental planning, persistent research context, and evidence-linked review [@doi:10.1038/s41586-025-09442-9; @arxiv:2505.13400; @doi:10.1038/s43588-025-00906-6; @arxiv:2607.13220; @arxiv:2602.19810v3]. These approaches demonstrate the value of structured coordination and persistent context. Most, however, organize that coordination within a particular multi-agent architecture or research environment. A different practical problem arises when a scientist works directly with separate interactive AI services over an extended project and must decide what each system should examine, when another system should review it, which evidence governs the next step, and what becomes accepted project state.

To address this problem, we developed **SCUTER (Scientific Collaboration for User-directed, Traceable, Evidence-based Research)**, a workflow for sustained scientific collaboration across AI platforms. The human investigator, termed the **User**, retains responsibility for the scientific question, assignment of work, interpretation of evidence, changes in project direction, and acceptance of results. AI participants can propose, implement, analyze, test, review, challenge, and revise work, but their contributions are connected through a shared scientific collaboration record to the methods, sources, versioned artifacts, execution evidence, reviews, and decisions needed to understand how the work developed. Explicit handoffs allow work to continue across sessions, while the User determines which information governs the next task and which results become part of the accepted project state.

The workflow was developed during one investigator's sustained coordination of GPT and Claude across active scientific projects using Notion as a shared collaboration record and GitHub for versioned artifacts. We retrospectively examined a frozen corpus of 728 records from seven standardized Collaboration Logs across six active workspaces to characterize how the workflow was used, where continuity and verification failed, and which practices emerged in response. We also assessed how the recorded workflow and its linked artifacts supported FAIR-oriented research practice. This is a descriptive single-investigator case rather than a controlled comparison of AI systems, and the subsequently packaged SCUTER Skill was not evaluated within the frozen corpus. The contribution is therefore an operational framework and reusable resource for scientists who want to use collaborative AI while retaining a rigorous, inspectable, and User-directed scientific record.


# Methods

## Workflow development and implementation

SCUTER was developed iteratively during sustained scientific work by one investigator using paid interactive versions of ChatGPT and Claude rather than model APIs. The two AI systems participated across active research projects in activities that included literature review, software development, analysis, interpretation, scientific review, documentation, and product development. The investigator, termed the **User**, retained authority over the scientific questions, access to project resources, assignment and redirection of work, interpretation of evidence, acceptance of results, and release of research products. GPT and Claude took task-dependent lead and review roles, and these roles could reverse between work units.

Notion Business served as the shared scientific collaboration workspace across the participating AI systems and the User. As the workflow developed, projects used a Project Overview or other current-state record together with a structured Collaboration Log and additional scientific notebooks or working records as needed. Collaboration Log entries recorded the purpose and assignment of substantive work, methods and results, links to supporting sources and artifacts, review and acceptance state, relevant decisions, and the next action. Page bodies provided space for detailed methods, results, source checks, review findings, and other scientific context. The shared record therefore connected individual contributions to the information needed to interpret them and carried project state across AI sessions. Both AI platforms could retrieve and write to the shared Notion record through their available integrations when prompted by the User.

GitHub was used for versioned research products, including source code, configuration, tests, figures, documentation, and other project artifacts. Scientific computation remained in User-controlled environments when authoritative execution or controlled data access was required. Records linked computational results to the relevant repository revision, inputs, configuration, command, execution environment, and outputs when those materials were needed to inspect or reproduce the result. This separation allowed the collaboration record to describe why work was undertaken and what had been accepted, GitHub to identify versioned product state, and the execution record to document what was actually run.

For later manuscript production, the User extended this product-oriented approach using Manubot, a GitHub-based scholarly writing workflow in which manuscript source is maintained as version-controlled text and automated actions generate publication-ready documents [@doi:10.1371/journal.pcbi.1007128]. Conventional document-authoring environments available to the project, including Google Docs, Microsoft Word, and Overleaf, did not provide the participating GPT and Claude systems with comparable direct editing access in the implementation used here. Notion remained useful for the scientific collaboration record, while Manubot allowed the User and both AI participants to retrieve and edit common manuscript source, inspect exact revisions through Git history and diffs, and maintain a versioned product throughout manuscript development.

The operating practices evolved over several weeks of active project work as recurring coordination and verification needs became apparent. Problems encountered during use included sessions beginning without the governing project state, claims or analyses lacking supporting evidence, discrepancies between collaboration records and stored artifacts, incomplete execution records, inaccessible or misplaced files, and uncertainty about which revision had been reviewed or accepted. In response, the workflow increasingly used bounded assignments, explicit links to governing context, artifact and source verification, task-dependent reciprocal review, structured handoffs, maintenance of accepted project state, and explicit User decisions about acceptance and scientific redirection. These practices were refined through use across projects rather than introduced as a complete protocol at project outset.

Once the recurring practices were sufficiently stable for reuse, they were formalized as **SCUTER (Scientific Collaboration for User-directed, Traceable, Evidence-based Research)** and subsequently packaged as an Agent Skill, together with a complete Markdown edition for systems that accept document-based instructions. The Skill provides reusable operating instructions, templates, review procedures, and implementation guidance derived from the workflow. The retrospective corpus described below captures the scientific collaboration process from which these practices emerged; the packaged Skill represents the subsequent formalization of that experience into a reusable implementation. Detailed schemas, templates, configuration information, and adoption procedures are provided in the Supplementary Material.

## Retrospective evaluation

We conducted a retrospective descriptive case study of one User coordinating GPT and Claude across private scientific workspaces that used the structured Collaboration Log. Before extraction, a fixed analytical cutoff was established and the eligible records were frozen for analysis. The resulting corpus contained **728 records from seven standardized Collaboration Logs across six active workspaces**. Freezing the corpus established a common analytical boundary while the underlying scientific projects continued to develop. Logs using substantially different structures were retained as contextual information but were excluded from the standardized corpus. The manuscript-development Collaboration Log was created after the analytical boundary and was examined separately as a subsequent example of the workflow in use.

The retrospective analysis used the structured Collaboration Logs and the scientific records and artifacts linked from them. Project-specific scientific findings were withheld to protect private research and collaborators. Instead, the analysis examined collaboration functions represented in the records, including task assignment and lead or review roles, reciprocal correction, handoffs and session continuity, management of accepted project state, literature and citation checking, code and analysis review, artifact and execution evidence, and operational problems that motivated subsequent corrective practices. The analysis was qualitative and descriptive. Because synchronized exports of the underlying chat conversations were not part of the study record, the unit of examination was the durable collaboration record rather than individual conversational exchanges, and interaction-level frequencies or timing measures were not estimated.

The corpus spanned multiple model releases and platform configurations. Historical records were associated with a specific model version only when that information had been documented at the time. Tasks were assigned by the User according to project needs rather than randomized or matched between platforms. The retrospective analysis therefore characterizes how the workflow operated within one investigator's sustained scientific practice. Prospective studies across investigators, scientific domains, platform combinations, and assignment strategies will be needed to evaluate general performance and comparative effectiveness.

We separately assessed how the recorded workflow and its linked research products supported FAIR-oriented research practice. Because the FAIR principles apply to digital research objects, the assessment focused on whether the collaboration record helped preserve and connect information needed to make scientific products findable, accessible, interoperable, and reusable [@doi:10.1038/sdata.2016.18]. The materials examined included Collaboration Logs, notebooks and accepted-state records, handoffs, repository and commit identifiers, code and configuration records, execution evidence, citation-validation records, and artifact locations.

For **Findability**, we examined searchable descriptions and stable identifiers that exposed the location and state of research objects. For **Accessibility**, we examined documented access conditions and whether intended participants could retrieve the referenced records and artifacts. For **Interoperability**, we examined repeated machine-readable fields and identifiers used to connect records and artifacts across platforms and storage systems. For **Reusability**, we examined preservation of scientific rationale, provenance, execution information, limitations, review history, and links to supporting materials. A feature was counted as documented support when the relevant record or linked object was present and retrievable in the study materials. Missing or inaccessible artifacts, incomplete execution information, invalid identifiers or checksums, and other documented limitations were recorded as incomplete support. Findings were summarized descriptively rather than combined into a numerical FAIR score.


# Results

## Scientific work across SCUTER projects

The frozen corpus contained 728 records from seven SCUTER-standardized Collaboration Logs across six active scientific workspaces. Log entries spanned the full scientific task cycle: research questions were defined and revised, literature was reviewed, analyses and software were developed, results were interpreted, and manuscripts or other research products were prepared. As in any scientific endeavor, these activities often overlapped, and later findings sometimes required earlier assumptions or analyses to be reconsidered.

The research phases in the SCUTER cycle can be broadly categorized as: 1. project setup, 2. scientific planning, 3. organization of research materials, 4. literature review, 5. active research, 6. product development, and 7. release or archiving. Projects moved in and out of these phases as the research progressed.

Individual tasks within different phases followed a similarly recurring pattern: the User assigned or redirected work, GPT or Claude followed directions and recorded the supporting evidence or artifacts, reviews occurred when appropriate, and the User decided what conclusions or revisions should be carried forward. Figure @fig:workflow summarizes how these individual tasks contributed to the larger course of a scientific project.

![SCUTER workflow for human-governed collaboration across AI platforms. The User can assign work to either Agent A or Agent B; work products and review findings are recorded through the Collaboration Log / Scientific Notebook; the User examines the accumulated record and review, decides whether to accept, reject, revise, or reassign, and accepted work is integrated into versioned artifacts.](images/Figure1.svg){#fig:workflow width=100%}

## User-guided assignments

Either GPT or Claude could be assigned to any task by the User, based on a project's scientific need. Either agent could subsequently review work produced by the other. In SCUTER, there is no assumed, fixed division of labor between the agents, and it is up to the User to decide on assignments.

Repeated assignments, corrections, and project-specific context also progressively focused each agent on the User's scientific problem. We refer to this as User-directed task specialization: the project's record increasingly focused the agents through scientific instructions, evidence, prior decisions, and feedback.

The Collaboration Logs allowed work to move asynchronously between AI systems and between chat sessions without requiring direct communication between them. The User evaluated the reviews, requested additional work when needed, and determined which conclusions should be carried forward.

## Problems identified during use

The Collaboration Logs also recorded problems that became apparent during sustained use of the workflow. Agents did not always record substantive work unless explicitly reminded by the User, and research artifacts could be lost when scripts or other intermediate products were generated and used without being preserved. Another recurring problem was an assumption of novelty before the relevant prior work had been established. Because an AI-generated statement cannot establish where an idea originated or whether comparable work already exists, claims of novelty require explicit review of the scientific literature and other relevant prior art. This is an efficiency  as well as a proper scientific conduct issue; aligning a research project with the literature avoids time wasted on re-discovering prior art.

Another challenge commonly faced with AI collaboration concerns scientific responsibility. The User must ultimately assume full responsibility for research products, but meaningful acceptance requires a record that can actually be reviewed both by the User and the scientific community. The Collaboration Log and associated notebooks provide a written account of what was done, what evidence and artifacts supported the work, what reviews occurred, and which conclusions were being carried forward. This gives the User a practical means to organize, review and explicitly accept the research record rather than relying on a transient sequence of AI conversations embedded in chat logs.

| Problem observed | Practice adopted |
| --- | --- |
| Agents failed to record substantive work consistently | Require substantive work to be recorded in the Collaboration Log, with User review when entries are missing |
| Scripts and other research products were not always preserved after use | Create a version-controlled repository at project initiation and preserve research products, including small intermediate artifacts |
| Agents could assume or assert novelty without establishing prior art | Require thorough prior-art searches before making novelty claims, record supporting sources, and revisit prior art as the research develops |
| The User could not meaningfully accept responsibility for work that was not presented in a reviewable record | Maintain a readable research record of methods, evidence, artifacts, reviews, decisions, and accepted conclusions so the User can provide documented informed acceptance |
| Claims or analyses without adequate support | Link assertions to supporting evidence and verify the underlying sources |
| Differences between written records and stored files or results | Inspect and verify the referenced artifacts directly |
| Incomplete computational records | Record code version, inputs, configuration, commands, and outputs when needed for reproducibility |
| Uncertainty about whether work had been reviewed or accepted | Record review and acceptance status explicitly in the Collaboration Log |
| Files that could not be located or accessed | Verify artifact location and accessibility before relying on them |

These practices were added iteratively as problems were encountered rather than specified as a complete protocol at the beginning of the projects.

## Support for FAIR research practices

We assessed whether the Collaboration Logs and linked research products supported FAIR-oriented research practice. SCUTER provided places to record information relevant to all four FAIR principles: searchable descriptions and links helped locate research products; artifact locations and access conditions documented how materials could be retrieved; structured fields and persistent identifiers connected records across Notion, GitHub, and computational environments; and methods, evidence, versions, review history, and limitations provided information needed for later reuse.

| FAIR principle | Support observed in SCUTER records |
| --- | --- |
| Findable | Searchable log entries linked scientific work to files, repositories, commits, sources, and other research records |
| Accessible | Records identified where research products were stored and how intended participants could retrieve them |
| Interoperable | Repeated structured fields and identifiers connected records and artifacts across the tools used in the projects |
| Reusable | Records retained scientific rationale, methods, evidence, versions, review history, and limitations needed to interpret or reproduce prior work |

FAIR support depended on the completeness of the research record. Unlogged work, missing artifacts, incomplete execution information, and inaccessible files reduced that support. SCUTER therefore did not make a research project FAIR automatically; it provided a structure in which information needed for FAIR research practice could be recorded, reviewed, and corrected.


# Discussion

SCUTER developed from a practical problem in scientific use of general-purpose AI: how to generate helpful, reliable, high-quality research output when the quality of open-ended scientific work can be difficult to judge from an interactive session alone. A model can produce plausible analyses, literature interpretations, code, or scientific prose while still making substantive errors. The approach taken here was not to assign a general quality score to an AI system, but to turn individual pieces of scientific work into a formalized, modular process that is more inspectable and traceable. Tasks were bounded by the User, linked to supporting evidence and artifacts, reviewed when appropriate, and explicitly accepted or redirected. Related work has independently emphasized formalized research protocols and constraints on delegated AI work [@doi:10.64898/2026.03.02.709102; @arxiv:2606.17099]. SCUTER applies those principles to sustained work in which a scientist directs separate interactive AI systems across an evolving research project.

Repeated assignments also produced what we describe as **User-directed task specialization**. GPT and Claude remained general-purpose systems, but their work became increasingly focused on a particular scientific problem through project-specific instructions, evidence, terminology, corrections, accepted decisions, and prior work retained in the shared record. Specialized roles and selective context have precedents in multi-agent and scientific-agent systems [@arxiv:2308.00352; @arxiv:2307.07924; @doi:10.1038/s43588-025-00906-6]. In SCUTER, however, specialization is directed by the scientist across separate AI services rather than fixed within a single agent architecture. This may reduce repeated reorientation and irrelevant exploration, but the present retrospective study did not measure accuracy, token use, time, or efficiency. Whether progressive specialization improves scientific research performance and output is therefore a testable hypothesis rather than a demonstrated result.

Reciprocal reviews between agents and the User provide another opportunity to detect errors, but they should not be treated as proof of correctness or independence. A second AI system can examine the same bounded task, evidence, code, or interpretation and identify problems that the first system missed. Errors across language models can nevertheless remain correlated even across architectures and providers [@arxiv:2506.07962]. Agreement between GPT and Claude is therefore not itself scientific validation. The supporting evidence remains more important than agreement and must ultimately be evaluated by the User. Prior exposure also matters: the order in which task-relevant information is revealed can influence subsequent judgment [@doi:10.1016/j.fsisyn.2021.100161]. Future evaluations of multi-AI review should therefore distinguish genuinely separate review from review performed after one agent has already seen another agent's conclusion.

This emphasis on evidence also changes the role of the research record. Provenance work for AI agents increasingly treats retrieved evidence, tool outputs, intermediate claims, actions, and final responses as linked parts of an auditable execution history [@arxiv:2606.04990]. In SCUTER, the Collaboration Log serves a related function at the project level by showing what was done, which evidence and artifacts support it, what review occurred, and which decisions are being carried forward. This record is also central to scientific responsibility and FAIR-oriented practice. The User ultimately takes responsibility for research products, but meaningful acceptance requires a record that can be inspected before work is incorporated into the research project. The records examined here supported findability, accessibility, interoperability, and reusability when products were linked to searchable descriptions, stable identifiers, artifact locations, methods, versions, evidence, and review history. Missing logs, inaccessible artifacts, or incomplete execution records weakened that support. FAIR-oriented AI collaboration therefore depends on preserving the scientific record as work occurs, with the User monitoring whether agents record substantive work and preserve project artifacts rather than attempting to reconstruct provenance later.

A focused example arose after the retrospective cutoff during preparation of this manuscript. The Notion citation ledger and repository-side citation-validation record had diverged as references were added and reviewed, leaving completed validations represented differently across the two records. Neither AI participant recovered the discrepancy from memory. The User directed reconciliation against the accepted Collaboration Log, GPT reconstructed the intended states, and Claude independently checked the result before the ledger, repository metadata, and CI-built bibliography were brought back into agreement. This episode is outside the 728-record analytical corpus and is not evidence for the retrospective findings, but it illustrates how a durable record can support recovery when tools and records evolve asynchronously. More generally, SCUTER differs from systems in which coordination and shared memory reside primarily within the agent architecture. Shared workspaces, memory, and approval gates have been studied in multi-agent settings, including with model-simulated collaborators [@arxiv:2606.18413]. In SCUTER, the scientist remained the integrating participant who determined what each AI should examine, when review was needed, which artifacts governed the next step, and what work should be accepted.

The study has important limitations. The 728 records represent one investigator's use of GPT and Claude across six workspaces, not 728 independent observations. There was no control condition, randomized assignment, blinding, or prospectively defined measure of AI quality. Full synchronized chat histories were not part of the frozen corpus, historical model identities were incompletely recorded, and task exposure was not controlled. We therefore cannot separate the effects of the shared record, User coordination, reciprocal review, provider diversity, or the investigator's scientific expertise, nor can we conclude that SCUTER produces more accurate, faster, or less expensive research than ordinary use of one AI system or another collaborative workflow. The workflow also required active User maintenance. Agents sometimes failed to record substantive work unless reminded, research artifacts required deliberate preservation, and novelty claims required explicit prior-art searching. The implementation depended on commercial AI services, Notion, GitHub, and connector capabilities that may change over time. The subsequently packaged SCUTER Skill was created after the retrospective corpus and has not yet been evaluated as an adoption mechanism.

SCUTER is technically lightweight but is not necessarily resource-light. The implementation studied required no custom multi-agent platform, orchestration server, or API infrastructure; the User worked through interactive AI interfaces, a shared scientific record, GitHub, and existing computing environments. Once established, assigning work, requesting review, and recording acceptance were comparatively simple, although scientific oversight remained an active User responsibility. Financial requirements can nevertheless be substantial depending on the AI services, subscription tiers, usage levels, and recordkeeping tools chosen. In the implementation studied, the AI systems represented the major expense while the shared record was comparatively inexpensive. Lower-cost implementations could use less expensive subscription tiers, use a higher-capacity system for primary work and a lower-cost system for review, or substitute other shared-record tools. These alternatives may improve accessibility but were not evaluated here and should not be assumed to provide equivalent usage capacity, context handling, tool access, or scientific performance.

The broader resource costs of AI-assisted research also warrant consideration. Computational use has environmental and societal costs, and the scientific benefit of extensive AI use should be weighed against the resources consumed. Efficient workflows that avoid unnecessary repetition may therefore be valuable beyond their financial cost. By preserving prior analyses, evidence, corrections, and decisions in a durable record, SCUTER could reduce some repeated work that would otherwise have to be reconstructed across sessions. This potential benefit was not measured in the present study and should be evaluated alongside monetary and computational resource use.

Prospective evaluation should now test the questions that this descriptive study could not answer. Investigators who did not develop SCUTER could be asked to establish a project, complete task-review-acceptance cycles, recover work through handoffs, and locate the evidence supporting an accepted result. Comparisons could include ordinary single-AI use, multiple sessions from one provider, the two-provider SCUTER workflow, lower-cost SCUTER configurations, and more automated agent systems. Outcomes should include substantive defect detection, completeness of provenance, reproducibility of accepted results, successful artifact retrieval, time to acceptance, revision burden, User review time, and monetary or computational cost. Such studies could directly test whether User-directed task specialization improves the quality or efficiency of scientific AI work and whether lower-cost implementations retain the benefits observed in the present configuration.

The present study therefore supports a narrower conclusion. Sustained, useful, and responsible scientific collaboration with AI requires more than a capable model and a long conversation. It requires a way to connect assignments, evidence, artifacts, reviews, corrections, and scientific decisions across time and across systems. SCUTER provides one practical implementation in which those connections remain directed and ultimately accepted by the scientist responsible for the research.


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>

