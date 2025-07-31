---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      username: admin
      text: ""
      button:
        text: Download CV
        url: uploads/resume.pdf
    design:
      css_class: dark
      background:
        color: black
        image:
          filename: stacked-peaks.svg
          filters:
            brightness: 1.0
          size: cover
          position: center
          parallax: false

  - block: markdown
    id: research
    content:
      title: "📚 My Research"
      subtitle: ""
      text: |-
        Hi! I'm a Graduate Researcher at the <a href="https://coral-lab-asu.github.io/" target="_blank" rel="noopener">CoRAL Lab</a> at ASU. My work focuses on information retrieval, agentic LLM architectures, and large scale information synchronization.

        <div class="flex justify-between items-baseline gap-2 mt-8">
          <span class="font-bold text-[2rem]">Multi‑Hop Reasoning Agent — CoRAL Lab, ASU</span>
          <span class="font-bold text-[2rem] whitespace-nowrap">Feb 2025–Present</span>
        </div>
        Building a model‑agnostic multi‑hop QA agent for open‑ and closed‑book settings, integrating RAG, question decomposition, inference‑time scaling, and self‑verification. A custom LLM‑as‑Judge replaces EM/ROUGE and off‑the‑shelf LLM graders, directly assessing factual grounding, logical consistency, and chain coherence, and revealing where current benchmarks under-measure reasoning quality.
  
        - **Benchmarks/Datasets:** FanOutQA, Musique, Frames, Quest.
        - **Stack:** LangGraph, AutoGen, LangChain.
        - **Techniques:** RAG, decomposition, inference‑time scaling, self‑verification loops  
        - **Datasets:** FanOutQA, MuSiQue, Frames, QUEST  
        - **Goal:** Beat SOTA and reveal current benchmark weaknesses.  
      

        <div class="flex justify-between items-baseline gap-2 mt-12 mb-2">
          <span class="font-bold text-[2rem]">InfoboxIQ: Text to Infobox synchronization (Wikipedia) — CoRAL Lab, ASU</span>
          <span class="font-bold text-[2rem] whitespace-nowrap">Feb 2025–Present</span>
        </div>
        A multi-stage LLM pipeline for information synchronization (text‑to‑table). Takes a Wikipedia article and its infobox template and produces an updated, evidence‑grounded infobox. We also introduce an evaluation suite verifies that the synchronized table is faithful, complete, and non‑hallucinatory.

        - **Pipeline (6–8 stages):** Preprocess, key/property breakdown, QA‑SRL extraction, KG triple generation, KG merge and conflict resolution, infobox creation.
        - **Dataset:** ~90K article–infobox pairs across ~40 Wikipedia categories with manually annotated key schemas.
        - **Evaluation:** per‑key accuracy, coverage/completeness, hallucination rate, overall text‑to‑table sync quality.
    

  - block: markdown
    id: skills
    content:
      title: "🛠️ Technical Skills"
      subtitle: ""
      text: |-
        **Programming Languages & Frameworks:** Python, C/C++, MATLAB, Flask, FastAPI

        **Machine Learning:** PyTorch, TensorFlow, Keras, scikit-learn, Transformers, Hugging Face, OpenCV, pandas, NumPy

        **LLM/Agent & RAG Stack:** LangChain/LangGraph, AutoGen, ChromaDB, Pinecone, FAISS

        **Data Engineering & Databases:** Kafka, Spark, Airflow, MySQL, Postgres, MongoDB

        **Cloud & DevOps:** AWS, Docker, Git, CI/CD, MLflow
    design:
      css_class: wide

  - block: markdown
    content:
      title: "🎯 Selected Projects"
      subtitle: ""
      text: |-
        *Coming soon...*
    design:
      css_class: wide

  - block: markdown
    content:
      title: ""
      subtitle: ""
      text: |-
        **Check out my [projects](/projects/) and [work experience](/experience/)!**
    

  # - block: collection
  #   id: papers
  #   content:
  #     title: Featured Publications
  #     filters:
  #       folders:
  #         - publication
  #       featured_only: true
  #   design:
  #     view: article-grid
  #     columns: 2

  # - block: collection
  #   content:
  #     title: Recent Publications
  #     text: ""
  #     filters:
  #       folders:
  #         - publication
  #       exclude_featured: false
  #   design:
  #     view: citation

  # - block: collection
  #   id: talks
  #   content:
  #     title: Recent & Upcoming Talks
  #     filters:
  #       folders:
  #         - event
  #   design:
  #     view: article-grid
  #     columns: 1

  # - block: collection
  #   id: news
  #   content:
  #     title: Recent News
  #     subtitle: ""
  #     text: ""
  #     page_type: post
  #     count: 5
  #     filters:
  #       author: ""
  #       category: ""
  #       tag: ""
  #       exclude_featured: false
  #       exclude_future: false
  #       exclude_past: false
  #       publication_type: ""
  #     offset: 0
  #     order: desc
  #   design:
  #     view: date-title-summary
  #     spacing:
  #       padding: [0, 0, 0, 0]

  # - block: cta-card
  #   demo: true
  #   content:
  #     title: "👉 Build your own academic website like this"
  #     text: |-
  #       This site is generated by Hugo Blox Builder - the FREE, Hugo-based open source website builder trusted by 250,000+ academics like you.

  #       <a class="github-button" href="https://github.com/HugoBlox/hugo-blox-builder" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star HugoBlox/hugo-blox-builder on GitHub">Star</a>

  #       Easily build anything with blocks - no-code required!
        
  #       From landing pages, second brains, and courses to academic resumés, conferences, and tech blogs.
  #     button:
  #       text: Get Started
  #       url: https://hugoblox.com/templates/
  #   design:
  #     card:
  #       css_class: "bg-primary-700"
  #       css_style: ""
---
