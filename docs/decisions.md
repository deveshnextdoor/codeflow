\# CodeFlow — Product Decisions



\## Decision 1 — Android-first



\*\*Decision:\*\* Build and validate CodeFlow as an Android-first product.



\*\*Why:\*\* The target experience is short, frequent, mobile learning. Android is the initial platform and keeps the pilot focused.



\*\*Trade-off:\*\* Web and iOS are not initial targets.



\*\*Revisit when:\*\* The core learning loop has been validated with the pilot.



\---



\## Decision 2 — User-selected learning paths



\*\*Decision:\*\* Users can choose from available learning paths and switch between them at any time.



\*\*Initial paths:\*\* Python, C, C++.



\*\*Why:\*\* CodeFlow should feel like a learning platform rather than a single fixed course. Users may pause one path and continue another without losing progress.



\*\*Rule:\*\* Each learning path maintains independent progress, mastery and review state.



\---



\## Decision 3 — One current learning path at a time



\*\*Decision:\*\* Users can have multiple saved learning paths, but the learning feed has one current path at a time.



\*\*Why:\*\* This provides flexibility without mixing unrelated subjects inside a single learning session.



\---



\## Decision 4 — Card-based learning



\*\*Decision:\*\* The core learning unit is a short interactive card.



\*\*Initial card types:\*\*



\- Concept

\- Code

\- Quiz

\- Spot the Bug



\*\*Why:\*\* Cards support short sessions and allow different forms of learning and assessment without requiring long-form lessons.



\---



\## Decision 5 — Hybrid learning model



\*\*Decision:\*\* The curriculum provides a structured sequence, while practice cards can be selected adaptively.



\*\*Why:\*\* A fully fixed sequence is predictable but cannot respond to weaknesses. A fully adaptive curriculum is unnecessarily complex for the pilot.



\---



\## Decision 6 — Problem solving is a first-class outcome



\*\*Decision:\*\* CodeFlow should not optimize only for recall or quiz completion.



Users should progressively be able to:



1\. Understand concepts

2\. Recall important information

3\. Read and reason about code

4\. Identify bugs

5\. Solve small programming problems



\*\*Why:\*\* The product goal is practical understanding rather than lesson completion alone.



\---



\## Decision 7 — Hand-written content first



\*\*Decision:\*\* Initial educational content will be written and verified manually.



\*\*Why:\*\* Educational correctness is more important than content-generation speed during the pilot.



\---



\## Decision 8 — Seed content before backend complexity



\*\*Decision:\*\* Start with a small, controlled content set before expanding the content system.



\*\*Why:\*\* The pilot needs enough high-quality content to test the learning loop, not a large content catalog.



\---



\## Decision 9 — AI comes later



\*\*Decision:\*\* No AI feature is required for the pilot.



AI may eventually assist with tutoring, personalization, content generation or feedback, but those uses will be evaluated only after the core learning experience has been validated.



\*\*Why:\*\* AI introduces correctness, consistency and evaluation problems before the core learning experience has been validated.



\---



\## Decision 10 — Events from day one



\*\*Decision:\*\* Product and learning events are recorded from the beginning.



\*\*Why:\*\* Pilot metrics such as retention, session length, card performance and adaptive-vs-random comparisons require reliable behavioural data.



\---



\## Decision 11 — Gamification supports learning



\*\*Decision:\*\* XP and streaks are included, but they are secondary to learning outcomes.



\*\*Why:\*\* Engagement mechanics should encourage consistent practice without becoming the product's primary objective.



\---



\## Decision 12 — Small pilot before expansion



\*\*Decision:\*\* Validate the learning loop with approximately 12–50 users before significantly expanding the catalog or feature set.



\*\*Why:\*\* A small pilot allows fast iteration and prevents investing heavily in features before there is evidence that the core experience works.



\---



\## Decision 13 — No implementation folders during Phase 0



\*\*Decision:\*\* Phase 0 contains product/design documentation only.



The repository should contain the README and `/docs` files, with no application, backend or monorepo implementation folders.



\*\*Why:\*\* Separating product definition from implementation keeps Phase 0 focused and prevents premature architecture decisions.



\---



\## Decision 14 — User progress is independent by topic



\*\*Decision:\*\* Switching from Python to C or C++ must never reset or overwrite progress.



Each topic maintains its own:



\- Mastery

\- Card history

\- Review state

\- Attempts

\- Topic progress



\*\*Why:\*\* Users should be able to explore different learning paths while retaining their previous work.

