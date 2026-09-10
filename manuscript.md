---
title: 'SCUTER: Scientific Collaboration for User-directed, Traceable, Evidence-based Research'
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
  <meta name="dc.title" content="SCUTER: Scientific Collaboration for User-directed, Traceable, Evidence-based Research" />
  <meta name="citation_title" content="SCUTER: Scientific Collaboration for User-directed, Traceable, Evidence-based Research" />
  <meta property="og:title" content="SCUTER: Scientific Collaboration for User-directed, Traceable, Evidence-based Research" />
  <meta property="twitter:title" content="SCUTER: Scientific Collaboration for User-directed, Traceable, Evidence-based Research" />
  <meta name="dc.date" content="2026-09-10" />
  <meta name="citation_publication_date" content="2026-09-10" />
  <meta property="article:published_time" content="2026-09-10" />
  <meta name="dc.modified" content="2026-09-10T16:07:51+00:00" />
  <meta property="article:modified_time" content="2026-09-10T16:07:51+00:00" />
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
  <link rel="alternate" type="text/html" href="https://TaylorResearchLab.github.io/scuter-manuscript/v/60f57b450bf9c800f185099a00a97ae51af38e20/" />
  <meta name="manubot_html_url_versioned" content="https://TaylorResearchLab.github.io/scuter-manuscript/v/60f57b450bf9c800f185099a00a97ae51af38e20/" />
  <meta name="manubot_pdf_url_versioned" content="https://TaylorResearchLab.github.io/scuter-manuscript/v/60f57b450bf9c800f185099a00a97ae51af38e20/manuscript.pdf" />
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
([permalink](https://TaylorResearchLab.github.io/scuter-manuscript/v/60f57b450bf9c800f185099a00a97ae51af38e20/))
was automatically generated
from [TaylorResearchLab/scuter-manuscript@60f57b4](https://github.com/TaylorResearchLab/scuter-manuscript/tree/60f57b450bf9c800f185099a00a97ae51af38e20)
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


# Results


# Discussion


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>

