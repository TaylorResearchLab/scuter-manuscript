# SCUTER: Scientific Collaboration for User-directed, Traceable, Evidence-based Research

This repository contains the primary manuscript describing **SCUTER**, a workflow for sustained scientific collaboration across AI platforms while preserving human scientific authority, provenance, review, evidence, and continuity across sessions.

The paper describes how the workflow developed during sustained scientific work with GPT and Claude, presents the resulting SCUTER framework, and reports a retrospective descriptive evaluation of its use across structured scientific collaboration records.

**Latest built files:** [Manuscript PDF](https://github.com/TaylorResearchLab/scuter-manuscript/blob/output/manuscript.pdf) · [HTML manuscript](https://TaylorResearchLab.github.io/scuter-manuscript/)

## Manuscript

The manuscript source is maintained in [`content/`](content). The paper follows a streamlined scientific structure:

- Abstract
- Introduction
- Methods
- Results
- Discussion

GitHub Actions builds the manuscript directly from the `main` branch using Manubot and publishes the generated outputs through the `output` and `gh-pages` branches.

## SCUTER

**SCUTER (Scientific Collaboration for User-directed, Traceable, Evidence-based Research)** is designed for sustained scientific work in which a human investigator coordinates contributions from one or more AI systems while retaining authority over scientific questions, governing context, evidence, interpretation, acceptance, and project direction.

The reusable SCUTER implementation is maintained in the [TaylorResearchLab/SCUTER](https://github.com/TaylorResearchLab/SCUTER) repository. It provides the Agent Skill package, complete Markdown instructions, templates, and implementation guidance for adopting the workflow.

## Manuscript collaboration

The manuscript itself is developed through the same general approach described in the paper. Scientific decisions, reviews, and handoffs are maintained in the shared collaboration record, while GitHub provides versioned manuscript source, exact diffs, commit history, and automated build evidence. GPT and Claude can contribute to and review versioned manuscript material under User direction, and the User retains scientific and publication authority.

## Public resources

- Manuscript source: [`content/`](content)
- Latest PDF: [manuscript.pdf on the `output` branch](https://github.com/TaylorResearchLab/scuter-manuscript/blob/output/manuscript.pdf)
- HTML manuscript: https://TaylorResearchLab.github.io/scuter-manuscript/
- SCUTER implementation: [TaylorResearchLab/SCUTER](https://github.com/TaylorResearchLab/SCUTER)
- GitHub Actions builds: [Actions](https://github.com/TaylorResearchLab/scuter-manuscript/actions)

## License

Manuscript text is intended for release under CC BY 4.0. Code and configuration follow the Manubot Rootstock licensing model.
