# CodeFlow — Scope

## Problem

Many people want to learn programming and computer science but are uncomfortable with long-form courses, lectures, and large study sessions. They want to learn something useful in small amounts of time while still reaching a point where they can understand concepts, answer questions, reason about code, find bugs, and solve problems.

CodeFlow is a gamified, mobile-first learning app designed around short daily learning sessions.

## Target Users

### Product audience

Anyone who wants to learn programming or computer science through short, repeatable sessions, including:

- Beginners learning programming
- Students learning CS alongside college
- Students revising programming concepts
- Self-learners who prefer interactive learning over long-form content

### Initial pilot audience

CS/IT students and beginner programmers.

The pilot audience is intentionally narrower so the learning experience can be evaluated with a relatively consistent group. The eventual product can support a broader audience.

## Value Proposition

> Learn programming in small daily steps — understand it, practice it, solve problems, and remember it.

The core learning loop is:

**Learn → Recall → Reason → Solve → Get feedback → Review**

Short sessions are the delivery mechanism, not the learning objective. CodeFlow should optimize for what the learner can eventually **do**, rather than how many lessons they complete.

## Product Positioning

CodeFlow is a **CS micro-learning + problem-solving mastery** platform.

Users choose what they want to learn. Each available topic provides its own structured learning path. Users can pause one path, switch to another, and return later without losing progress.

The learning feed has one current topic at a time, while progress for all selected topics is preserved independently.

## Differentiation

Existing products such as Mimo and SoloLearn already provide bite-sized programming lessons, quizzes, practice and gamification. CodeFlow therefore should not differentiate simply by being "short" or "gamified."

CodeFlow's intended distinction is the combination of:

- User-selected learning paths
- Short interactive learning units
- Prerequisite-aware progression within each path
- Code reading and reasoning
- Spot-the-bug practice
- Problem-solving puzzles
- Adaptive practice based on learner performance
- Progress measured through mastery rather than lesson completion alone

The key product question is:

> Can a short, adaptive, gamified learning loop help users consistently learn, retain, and apply programming concepts?

## V1.0 — IN

### Learning paths

Initial launch paths:

- Python
- C
- C++

Each path has its own progression and learner state.

### Card types

1. **Concept** — short explanation of one idea
2. **Code** — read and reason about code
3. **Quiz** — test recall and understanding
4. **Spot the Bug** — identify and reason about programming errors

The curriculum provides structure while practice cards can be selected adaptively.

### Product

- Android-first mobile experience
- Onboarding
- Topic/language selection
- Level selection
- Daily learning goal
- Learning feed
- Topic switching
- Independent progress for each learning path
- Progress/mastery view
- Profile/settings
- XP
- Streak
- Basic adaptive practice
- Basic spaced review

### Measurement

- Quiz accuracy over time
- D1 retention
- D7 retention
- Session length
- Cards per session
- Adaptive-feed vs random-feed comparison
- Event logging from day one

## V1.0 — OUT

The following are explicitly not part of the first version:

- Large catalog of programming/CS subjects
- User-generated content
- Social feed/community
- Leaderboards
- Multiplayer competitions
- Certificates
- Large coding projects
- Full IDE/development environment
- AI tutor
- AI-generated learning content
- AI-generated grading
- Voice/video lessons
- Web/desktop application
- Monetization/subscriptions
- Advanced personalization beyond the initial adaptive feed
- Production-scale cloud infrastructure

These may be considered later, but they are not required to validate the core learning loop.

## Product Principles

1. **Small sessions, real learning.** Short does not mean shallow.
2. **Active recall over passive consumption.**
3. **Problem solving is a first-class outcome.**
4. **Application matters.** Learners should eventually use concepts and syntax.
5. **Prerequisites matter within each learning path.**
6. **Gamification supports learning rather than replacing it.**
7. **Content quality beats content volume.**
8. **Users control what they learn.**
9. **AI comes later.** Initial educational content is written and verified manually.