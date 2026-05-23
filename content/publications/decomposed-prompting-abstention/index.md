---
title: 'Decomposed Prompting Does Not Fix Knowledge Gaps, But Helps Models Say "I Don''t Know"'

authors:
  - me
  - Lyuxin David Zhang
  - Dan Roth
  - Tomer Wolfson
  - Vivek Gupta

date: '2026-02-04T00:00:00Z'

# Schedule page publish date (NOT publication's date).
publishDate: '2026-05-23T00:00:00Z'

publication_types: ['paper-conference']

publication: 'In *Findings of the Association for Computational Linguistics: ACL 2026*'
publication_short: 'In *ACL 2026 Findings*'

abstract: |
  Large language models often struggle to recognize their knowledge limits in
  closed-book question answering, leading to confident hallucinations. While
  decomposed prompting is typically used to improve accuracy, we investigate
  its impact on reliability. We evaluate three task-equivalent prompting
  regimes: Direct, Assistive, and Incremental, across different model scales
  and multi-hop QA benchmarks. We find that although accuracy gains from
  decomposition diminish in frontier models, disagreements between prompting
  regimes remain highly indicative of potential errors. Because factual
  knowledge is stable while hallucinations are stochastic, cross-regime
  agreement provides a precise signal of internal uncertainty. We leverage this
  signal to implement a training-free abstention policy that requires no
  retrieval or fine-tuning. Our results show that disagreement-based
  abstention outperforms standard uncertainty baselines as an error detector,
  improving both F1 and AUROC across settings. This demonstrates that
  decomposition-based prompting can serve as a practical diagnostic probe for
  model reliability in closed-book QA.

summary: |
  Decomposed prompting does not reliably repair missing knowledge in
  closed-book QA, but disagreement across prompting regimes provides a strong
  signal for when models should abstain instead of hallucinating.

tags:
  - Large Language Models
  - Reliability
  - Hallucination
  # - Abstention
  # - Question Answering
  - Multi-Hop Reasoning

featured: true

share: false

links:
  - type: preprint
    provider: arxiv
    id: 2602.04853
    label: Paper
  - type: code
    url: https://github.com/dhruvmadhwal/disagreement-based-abstention

image:
  caption: ''
  focal_point: ''
  preview_only: false

projects: []
slides: ""
---

Accepted to **Findings of ACL 2026**.

This paper asks a deceptively simple question: if we break a hard question into smaller steps, do language models actually become more reliable, or do they just sound more organized while making the same mistakes?

We study this in the setting of closed-book question answering, where the model has to rely on what it already knows rather than external retrieval. While decomposed prompting is often treated as a way to improve reasoning, our results show a more nuanced story: decomposition does not consistently fix underlying knowledge gaps, especially in stronger frontier models. What it *does* provide is a highly useful diagnostic signal.

Across direct, assistive, and incremental prompting regimes, we find that disagreements between prompting strategies are strongly associated with potential errors. Since genuine factual knowledge tends to stay stable across formulations while hallucinations are much more stochastic, this disagreement becomes a practical indicator of when a model should say "I don't know."

Using that observation, we build a training-free abstention policy that does not require retrieval or fine-tuning. The result is a simple but effective method for improving reliability in closed-book QA by helping models abstain more appropriately when they are uncertain.

If you'd like to read the paper, you can find the preprint on arXiv [here](https://arxiv.org/abs/2602.04853). The code for the disagreement-based abstention setup is available [here](https://github.com/dhruvmadhwal/disagreement-based-abstention).
