CodeFlow — Product Decisions

Decision 1 — Android-first

Decision: Build and validate CodeFlow as an Android-first product using React Native (Expo).

Why: The target experience is short, frequent, mobile learning. Android is the initial platform and keeps the pilot focused. React Native (Expo) allows the mobile app to be developed without committing to a native Android-only implementation.

Trade-off: Web and iOS are not initial targets.

Revisit when: The core learning loop has been validated with the pilot.

Decision 2 — User-selected learning paths

Decision: Users can choose from available learning paths and switch between them at any time.

Initial pilot paths: Python and C.

Stretch path: C++.

Why: CodeFlow should feel like a learning platform rather than a single fixed course. Users may pause one path and continue another without losing progress.

Rule: Each learning path maintains independent progress, mastery and review state.

Decision 3 — One current learning path at a time

Decision: Users can have multiple saved learning paths, but the learning feed has one current path at a time.

Why: This provides flexibility without mixing unrelated subjects inside a single learning session.

Decision 4 — Card-based learning

Decision: The core learning unit is a short interactive card.

Initial card types:

Concept

Code

Quiz

Spot the Bug

No fifth card type is required for V1.

Why: Cards support short sessions and allow different forms of learning and assessment without requiring long-form lessons.

Decision 5 — Hybrid learning model

Decision: The curriculum provides a structured sequence, while practice cards can be selected adaptively.

Why: A fully fixed sequence is predictable but cannot respond to weaknesses. A fully adaptive curriculum is unnecessarily complex for the pilot.

Decision 6 — Problem solving is deferred from V1

Decision: V1 focuses on understanding concepts, recall, code reasoning, bug spotting, practice and retention. General programming problem-solving tasks are deferred.

V1 learning loop:

Learn → Recall → Reason → Practice → Get feedback → Review

Potential problem-solving formats are reserved for V2, including:

Arrange-the-lines

Fill-the-missing-line

Write-a-function with a sandbox

Why: Keeping problem-solving tasks out of V1 protects the pilot scope and allows the core learning and mastery loop to be validated first.

Decision 7 — Positioning focuses on code reasoning and mastery

Decision: CodeFlow is positioned around CS micro-learning, code reasoning and debugging mastery rather than short lessons or gamification alone.

Key intended differentiators:

Prerequisite-aware progression

Code reading and reasoning

Spot-the-bug practice

Adaptive practice based on learner performance

Mastery-oriented progress

Why: Bite-sized programming lessons, quizzes and gamification are already common in existing learning products. CodeFlow needs a clearer learning-focused distinction.

Decision 8 — Hand-written content first

Decision: Initial educational content will be written and verified manually.

Why: Educational correctness is more important than content-generation speed during the pilot.

Decision 9 — Seed content before backend complexity

Decision: Start with a small, controlled content set before expanding the content system.

Pilot content target:

6 concepts per language

8 cards per concept

1 Concept card

2 Code cards

3 Quiz cards

2 Spot-the-Bug cards

Approximately 48 cards per language

Approximately 96 cards total for Python and C

Each concept should have at least 3 quiz cards so delayed-accuracy checks can use a different question from initial practice where possible.

Why: The pilot needs enough high-quality content to test the learning loop, not a large content catalog.

Decision 10 — AI comes later

Decision: No AI feature is required for the pilot.

AI may eventually assist with tutoring, personalization, content generation or feedback, but those uses will be evaluated only after the core learning experience has been validated.

Why: AI introduces correctness, consistency and evaluation problems before the core learning experience has been validated.

Decision 11 — Events from day one

Decision: Product and learning events are recorded from the beginning.

Why: Pilot metrics such as retention, session length, card performance and adaptive-vs-random comparisons require reliable behavioural data.

Decision 12 — Gamification supports learning

Decision: XP and streaks are included, but they are secondary to learning outcomes.

Why: Engagement mechanics should encourage consistent practice without becoming the product's primary objective.

Decision 13 — Small pilot before expansion

Decision: Validate the learning loop with approximately 12–50 users before significantly expanding the catalog or feature set.

Why: A small pilot allows fast iteration and prevents investing heavily in features before there is evidence that the core experience works.

Decision 14 — No implementation folders during Phase 0

Decision: Phase 0 contains product/design documentation only.

The repository should contain the README and /docs files, with no application, backend or monorepo implementation folders.

Why: Separating product definition from implementation keeps Phase 0 focused and prevents premature architecture decisions.

Decision 15 — User progress is independent by topic

Decision: Switching between Python, C or later C++ must never reset or overwrite progress.

Each topic maintains its own:

Mastery

Card history

Review state

Attempts

Topic progress

Why: Users should be able to explore different learning paths while retaining their previous work.

Decision 16 — Pilot scope is explicitly constrained

Decision: V1 excludes large catalogs, user-generated content, social/community features, leaderboards, multiplayer, certificates, large coding projects, a full IDE, AI-generated grading, voice/video lessons, a learner-facing web app, monetization, advanced personalization and production-scale cloud infrastructure.

Post-V1 stretch:

Admin dashboard

AI-generated content pipeline

AI tutor (RAG)

These are not dependencies for the pilot.

Why: The pilot should validate the learning loop before expanding product surface area or infrastructure complexity.

Decision 17 — Phase order protects the pilot

Decision: The roadmap should complete Phase 12 (Polish) and Phase 13 (Evaluate & Release) before Phase 10 (Admin + AI content) and Phase 11 (RAG tutor).

Why: Admin tooling and AI features are post-V1 stretch work. They should not become dependencies for shipping or evaluating the core learning experience.

Decision 18 — Adaptive vs random experiment

Decision: The primary adaptive-vs-random experiment is a within-user paired comparison assigned at the Concept level.

Each user's Concepts within a Topic are divided into two balanced groups:

Adaptive-practiced Concepts

Random-practiced Concepts

Assignment uses:

a seeded shuffle

alternating adaptive/random assignment

a random starting policy for each user

The assignment is made once per Concept and stored as UserConceptMastery.practice_policy.

Primary outcome: Per-user paired difference in delayed quiz accuracy between adaptive-practiced and random-practiced Concepts.

Each Concept has one held-out delayed-check quiz that is never used for practice.

Reporting: Report raw adaptive and random outcomes and the paired differences. Treat the result as directional rather than conclusive because the pilot is small.

Fallback: A between-user adaptive-vs-random design may be used if the within-user assignment cannot be implemented reliably in time.

Why: The within-user design reduces variation between learners while Concept-level assignment keeps the practice condition stable.

Decision 19 — Onboarding skip uses explicit defaults

Decision: The onboarding Skip action bypasses the optional onboarding choices and starts the learner with these defaults:

Topic: Python

Level: I'm completely new

Daily goal: 10 minutes

The learner can change these choices later.

Why: Skipping should reduce friction without creating an undefined learner state.

Decision 20 — Pull requests use squash merge

Decision: Future pull requests into develop use squash merge.

Why: Squashing keeps the develop history concise and groups each completed change into a clean commit.

The Phase 0 PR was merged normally and does not need to be rewritten.

Decision 21 — Branch protection follows CI

Decision: Enable branch protection after Phase 1 CI is working.

Why: Protection rules are more useful once CI checks exist and can be required before merging. Enabling them earlier would add process without a meaningful automated check to enforce.