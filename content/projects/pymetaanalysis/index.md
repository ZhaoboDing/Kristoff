---
title: "PyMetaAnalysis"
date: 2026-07-22
description: "A pandas-first, auditable meta-analysis library for Python."
summary: "A pandas-first Python library that makes conventional study-level meta-analysis explicit, inspectable, and reproducible."
tags: ["Python", "Statistics", "Open Source"]
showBreadcrumbs: true
showTableOfContents: true
showRelatedContent: false
showPagination: false
---

**PyMetaAnalysis** is an open-source Python library for conventional study-level meta-analysis. I built it around a simple principle: a statistical result should be easy to use, but never opaque.

<div class="flex flex-wrap gap-3 my-6">
{{< button href="https://github.com/ZhaoboDing/PyMetaAnalysis" target="_blank" >}}
View source on GitHub
{{< /button >}}
{{< button href="https://zhaoboding.github.io/PyMetaAnalysis/" target="_blank" >}}
Read the documentation
{{< /button >}}
</div>

## Why I built it

Meta-analysis often begins with data already living in a pandas DataFrame, yet many workflows require reshaping that data around a tool's assumptions. Just as importantly, a pooled estimate alone is not enough: analysts need to understand which studies were included, how edge cases were handled, which methods were selected, and how the result can be reproduced.

PyMetaAnalysis keeps that full trail attached to the result. It accepts DataFrames, NumPy arrays, and ordinary Python sequences, and returns immutable result objects containing study effects, exclusions, weights, diagnostics, method choices, provenance, and structured reports.

## What it supports

- Generic effects supplied with a sampling variance or standard error
- Binary outcomes using odds ratios, risk ratios, and risk differences
- Continuous outcomes using mean differences and Hedges' *g*
- Common-effect, random-effects, and Mantel–Haenszel models
- REML, Paule–Mandel, and DerSimonian–Laird heterogeneity estimators
- Subgroup analysis, leave-one-out analysis, and cumulative meta-analysis
- Forest and funnel plots through optional Matplotlib integration
- JSON and Markdown reports designed for downstream use

## Designed for auditability

Rows excluded by missing-data or sparse-data policies remain visible, with stable identifiers and explicit exclusion reasons. Transformations—such as converting a standard error to a variance—are recorded in provenance. For ratio measures, model-scale values remain available alongside display-scale estimates.

The test suite combines hand calculations, statistical invariants, numerical edge cases, and committed reference results from R's `metafor` package. Continuous integration covers Python 3.10–3.13, strict typing and linting, documentation, and distribution builds.

## A small example

```python
import meta_analyze as ma

result = ma.meta_analysis(
    effect=[0.12, 0.35, -0.08, 0.21],
    variance=[0.04, 0.06, 0.03, 0.05],
    study=["Trial A", "Trial B", "Trial C", "Trial D"],
    model="random",
    tau2_method="REML",
)

print(result.summary())
print(result.study_results)
```

The distribution is named `PyMetaAnalysis`, while the import name is `meta_analyze`. The project is released under the MIT License and is currently in its early 0.x stage.
