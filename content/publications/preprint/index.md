---
title: "Concrete Jungle: Towards Concreteness Paved Contrastive Negative Mining for Compositional Understanding"
authors:
  - Eun Woo Im
  - me
  - Vivek Gupta
date: "2026-04-14T00:00:00Z"

# Schedule page publish date (NOT publication's date).
publishDate: "2026-05-23T00:00:00Z"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article"]

# Publication name and optional abbreviated publication name.
publication: "arXiv preprint arXiv:2604.13313"
publication_short: "arXiv 2026"

abstract: |
  Vision-Language Models demonstrate remarkable capabilities but often struggle
  with compositional reasoning, particularly around word order and attribute
  binding. In this work, we study how the quality of contrastive negatives
  shapes that weakness and argue that lexical concreteness is a key factor in
  constructing more informative training pairs. We introduce ConcretePlant to
  systematically manipulate perceptually grounded concepts and Cement loss to
  better balance easy and difficult pairs during optimization. Together, these
  ideas form Slipform, a framework that improves compositional understanding
  while also strengthening retrieval and probing performance.

# Summary. An optional shortened abstract.
summary: |
  We study how concreteness-aware negative mining can improve compositional
  understanding in vision-language models, and introduce ConcretePlant,
  Cement loss, and Slipform to make contrastive learning more informative.

tags:
  - Vision-Language Models
  - Compositional Reasoning
  - Contrastive Learning
  - CLIP 
  

featured: true

share: false

links:
  - type: preprint
    provider: arxiv
    id: 2604.13313
    label: Paper
  - type: code
    url: http://github.com/eunwooim/my_n2clip

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ''
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/projects/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

This preprint explores a simple but important question in vision-language
learning: what kinds of negative examples actually teach models to understand
composition rather than memorize shallow correlations?

<figure>
  <img src="concrete-jungle.png" alt="ConcretePlant and Slipform pipeline for concreteness-aware negative mining">
  <figcaption>
    ConcretePlant and Slipform generate concreteness-aware hard negatives to improve compositional learning in vision-language models.
  </figcaption>
</figure>

We focus on a persistent weakness in many vision-language models: they often
struggle when meaning depends on the precise arrangement of words or the
binding between attributes and objects. Rather than redesigning the whole
architecture, this work studies the data side of the problem and asks how to
construct better contrastive signals during training.

Our central idea is that lexical concreteness matters. Swapping or modifying
highly concrete concepts tends to create sharper semantic and visual
differences, which makes negative examples more informative for learning. On
top of that, we introduce a margin-based objective, Cement loss, to keep easy
examples from dominating optimization and crowding out harder compositional
cases.

Together, these ideas form Slipform, which improves compositional benchmarks
while also helping on retrieval and probing tasks. If you'd like to read the
paper, you can find the arXiv preprint [here](https://arxiv.org/abs/2604.13313).
