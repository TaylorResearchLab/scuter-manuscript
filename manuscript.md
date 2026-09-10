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
date-meta: '2026-09-10'
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
  <meta name="dc.date" content="2026-09-10" />
  <meta name="citation_publication_date" content="2026-09-10" />
  <meta property="article:published_time" content="2026-09-10" />
  <meta name="dc.modified" content="2026-09-10T20:51:15+00:00" />
  <meta property="article:modified_time" content="2026-09-10T20:51:15+00:00" />
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
  <link rel="alternate" type="text/html" href="https://TaylorResearchLab.github.io/scuter-manuscript/v/1cdb227497e82c762df060a227404ffeecd3bc80/" />
  <meta name="manubot_html_url_versioned" content="https://TaylorResearchLab.github.io/scuter-manuscript/v/1cdb227497e82c762df060a227404ffeecd3bc80/" />
  <meta name="manubot_pdf_url_versioned" content="https://TaylorResearchLab.github.io/scuter-manuscript/v/1cdb227497e82c762df060a227404ffeecd3bc80/manuscript.pdf" />
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
([permalink](https://TaylorResearchLab.github.io/scuter-manuscript/v/1cdb227497e82c762df060a227404ffeecd3bc80/))
was automatically generated
from [TaylorResearchLab/scuter-manuscript@1cdb227](https://github.com/TaylorResearchLab/scuter-manuscript/tree/1cdb227497e82c762df060a227404ffeecd3bc80)
on September 10, 2026.
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


# Discussion


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>

