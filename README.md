# MCAT-How? — A Reddit-grounded RAG copilot for MCAT study planning

If I had unlimited time and money, I’d study for the MCAT and take one serious shot at an old dream: medical school.
In reality, I’m a PM with bills, limited time, and a portfolio to build—so I turned that curiosity into a product prototype.

MCAT-How? is a Retrieval-Augmented Generation (RAG) system that synthesizes community-validated MCAT strategies (from Reddit) into actionable, citation-backed guidance tailored to a user’s context (background, time constraints, weaknesses).

# About me 

I’m Foong Ming, a Product Manager interested in building in healthcare. Open to opportunities.

# About this README

This README is divided into two parts. 
1. The first half contains all the PM's box of tools in developing a hypothesis into a product.
2. The second half contains all the tech bits of building an e2e prototype of a RAG system. 

# Product hypothesis

> "I want to study for the MCAT but I don't know how to start!"

This started from my own experience trying to figure out MCAT prep as an outsider, plus patterns I repeatedly saw in community discussions. I treated these as design hypotheses and translated them into product requirements and system behavior.


1. Hypothesis: Early-stage learners are blocked by ambiguity and overload (too many resources, conflicting sequencing).

- Requirement: Convert ambiguity into a first-week plan and clear materials sequence.

- Feature: Structured outputs (study plan, sequencing, next steps).


2. Hypothesis: Trust is the core adoption barrier for AI advice in high-effort domains.
- Requirement: Recommendations must be traceable to source evidence.
- Feature: Citation-backed answers with links to specific threads/comments.

3. Hypothesis: The “best” plan is highly conditional on constraints (hours/week, timeline, baseline, weak sections).
- Requirement: Adapt outputs to user context and request missing constraints when needed.
- Feature: Context-aware prompting + response templates.

4. Hypothesis: Plateaued learners need long-tail interventions that generic guides under-serve.
- Requirement: Retrieve from long-tail discussions and present multiple interventions with tradeoffs.
- Feature: Long-tail retrieval + “strategy menu” outputs.

5. Hypothesis: Users want compression and curation, not another reading backlog.
- Requirement: Synthesize consensus and highlight disagreements without losing nuance.
- Feature: Curated ingestion + dedup/diversity-aware retrieval + structured synthesis.

# User Personas 

## Persona A: Zero-context beginner

They’re new to the MCAT ecosystem and don’t know what “good prep” even looks like. Every guide seems to contradict the next, and they can’t tell what matters.

What they want from MCAT-How?

- A clear starting point: what to do first, what to ignore, and why
- A study plan that respects constraints (e.g., working full-time)
- Source links so they can verify advice and dig deeper

Typical questions: 
- “How do I start Psych/Soc from scratch while working full-time?”
- “If I have 10 weeks, how should I sequence AAMC, UWorld, and Anki?”

## Persona B: Struggling aspirant

They’ve been studying, but progress has stalled in specific areas (CARS plateau, P/S stagnation, timing problems). Generic “how to study” posts aren’t addressing the failure mode.

What they want from MCAT-How?
- Several credible strategies to test, not one generic answer
- Interventions tied to the specific bottleneck (with tradeoffs)
- Proof points from people who overcame similar plateaus

Typical questions
- “My CARS score is stuck—what did others do to break past 127?”
- “My P/S is flat despite Anki—what do high scorers change?”

# What I built
•	End-to-end RAG pipeline: ingestion → cleaning/chunking → embeddings → HNSW retrieval → synthesis with citations

•	Retrieval layer optimized for low-latency querying and iterative tuning (chunking, top-k, dedup/diversity)

•	Response layer optimized for product usefulness: plans, options, and tradeoffs grounded in retrieved sources

# Architecture 
HNSWLib 

# Data 
- acquired top posts using 
- extracted comment using 
- used script to bind together 
