\# CodeFlow — Data Model



\## Purpose



The data model describes what CodeFlow needs to remember about users, learning content, attempts, mastery, review state, gamification and product events.



The model is intentionally small for the pilot. It should support independent progress across Python, C and C++, adaptive practice and the pilot metrics without introducing a full course-management hierarchy.



\## Core Entities



\### User



Represents a learner.



Key fields:



\- `id`

\- `created\_at`

\- `daily\_goal\_minutes`

\- `current\_topic\_id`

\- `total\_xp`

\- `current\_streak`



\### Topic



Represents a selectable learning path such as Python, C or C++.



Key fields:



\- `id`

\- `name`

\- `description`

\- `language`

\- `status`



Each topic has independent learner progress.



\### Prerequisite



Represents prerequisite relationships within a learning path.



For v0.x, prerequisites should remain simple and may reference prerequisite cards/concepts rather than introducing a full course/module hierarchy.



Example:



```text

Python Variables

&#x20;     ↓

Python Conditions

&#x20;     ↓

Python Loops

&#x20;     ↓

Python Functions

