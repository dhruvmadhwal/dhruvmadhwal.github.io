---
title: Multi-Hop Reasoning Agent
date: 2025-06-01
links:
  - type: demo
    url: https://multi-hop-agent.streamlit.app/
  - type: code
    url: https://github.com/dhruvmadhwal/multi-hop-agent
tags:
  - AI Agent
  - LangGraph
  - LangChain 
  - RAG 
  - Python
  - Tavily
  - Streamlit
---

Large language models can answer many questions directly, but they often struggle when a question requires several connected steps. Research shows that breaking complex questions into smaller sub-questions can improve performance, especially when each step is supported by retrieved evidence instead of relying only on model memory ([Least-to-Most Prompting](https://arxiv.org/abs/2205.10625), [Self-Ask](https://arxiv.org/abs/2210.03350), [Question Decomposition for RAG](https://arxiv.org/abs/2507.00355)).

<!--more-->

## Why Multi-Hop Reasoning?

This project builds on that idea by creating a multi-agent question answering system for complex, multi-step questions. Instead of sending one large prompt to a model, the system decomposes the task, plans intermediate steps, retrieves evidence when needed, and synthesizes a final answer.

The goal is to produce answers that are grounded and traceable rather than purely guessed from model memory. This is useful for questions that require combining facts across domains such as sports, geography, literature, or current events.

For example, consider the question:

> What country is home to the city where the author of *Pride and Prejudice* was born?

A direct answer requires multiple connected steps:

1. Identify the author of *Pride and Prejudice*.  
   Answer: Jane Austen.
2. Find where Jane Austen was born.  
   Answer: Steventon, Hampshire.
3. Determine which country Steventon is in.  
   Answer: England.
4. Synthesize the final answer.  
   Final answer: England.

This kind of question is simple for a person, but it illustrates why multi-hop reasoning matters: the answer is not found in a single fact. The system has to connect several pieces of information in the right order.

## How the Agent Works

The agent coordinates several specialized components: a planner that decides how to approach the question, a retrieval step that gathers supporting information, a code execution step for calculations or data processing, and a synthesis step that produces the final answer.

It supports both closed-book reasoning and retrieval-augmented answering using RAG and live web search. It also includes state tracking and stall recovery, allowing the agent to continue through longer reasoning chains without getting stuck.

## Implementation

I implemented the system in Python using LangGraph and LangChain, with structured outputs through Pydantic and asynchronous execution using asyncio. I also built a Streamlit interface that shows the agent’s intermediate steps, making it easier to inspect how the final answer was reached.

Overall, this project was an experiment in making LLM-based question answering more reliable by combining decomposition, retrieval, tool use, and multi-agent orchestration.

If you want to try it yourself, check out the demo [here](https://multi-hop-agent.streamlit.app/). And if you'd like to take a closer look at the implementation, you can find the code [here](https://github.com/dhruvmadhwal/multi-hop-agent).
