\# Wireframe 02 — Learning Feed



\## Goal



Provide the learner with a focused, short learning session for their currently selected learning path.



The feed combines structured curriculum progression with adaptive practice.



The learner should always understand:



\- What they are learning

\- What card they are currently on

\- How much of today's session they have completed

\- What action they should take next



\---



\## Screen — Learning Feed



\### Header



Elements:



\- Current topic name

\- Topic switcher

\- Current streak

\- Daily session progress



Example:



&#x20;   Python                         🔥 6



&#x20;   Today · 6 cards

&#x20;   ███████░░░ 70%



\### Card



The main content area displays one learning card at a time.



The card displays:



\- Card type

\- Topic/concept

\- Main content

\- Code where applicable

\- Primary interaction

\- Estimated difficulty where useful



Example Concept Card:



&#x20;   CONCEPT



&#x20;   What is a variable?



&#x20;   A variable stores a value that

&#x20;   your program can use later.



&#x20;   Key idea:

&#x20;   A variable gives a value a name.



&#x20;   \[ Continue ]



\---



\## Card Types



The feed supports four card types:



\### Concept



Purpose:



Introduce or explain one concept.



Target time:



30–60 seconds.



Primary action:



`Continue`



\### Code



Purpose:



Help the learner read and reason about code.



Target time:



45–90 seconds.



Primary action:



Answer the associated question.



\### Quiz



Purpose:



Test recall and understanding.



Target time:



20–45 seconds.



Primary action:



Select an answer.



\### Spot the Bug



Purpose:



Help the learner identify and reason about programming errors.



Target time:



45–90 seconds.



Primary action:



Identify the bug and submit an answer.



\---



\## Learning Sequence



The curriculum determines the concepts the learner should encounter.



The adaptive layer determines which practice card should appear next.



Example:



&#x20;   Concept

&#x20;      ↓

&#x20;   Code

&#x20;      ↓

&#x20;   Quiz

&#x20;      ↓

&#x20;   Spot the Bug

&#x20;      ↓

&#x20;   Evaluate performance

&#x20;      │

&#x20;      ├── Strong understanding

&#x20;      │        ↓

&#x20;      │    Continue progression

&#x20;      │

&#x20;      └── Weak understanding

&#x20;               ↓

&#x20;          Additional practice



The exact card sequence does not have to be identical for every learner.



\---



\## Actions



\### Continue



Moves to the next card.



\### Answer



Submits the learner's response.



For quizzes and bug cards, the answer should lead to the feedback state.



\### Pause / Exit



Allows the learner to leave the session.



Progress already completed during the session is preserved.



\### Switch Topic



Opens the user's saved learning paths.



Example:



&#x20;   My Learning



&#x20;   Python

&#x20;   ███████░░░ 72%

&#x20;   Continue →



&#x20;   C

&#x20;   ████░░░░░░ 41%

&#x20;   Continue →



&#x20;   C++

&#x20;   ██░░░░░░░░ 18%

&#x20;   Continue →



Selecting another topic changes the current feed topic.



The previous topic's progress is preserved.



\---



\## Session Completion



When the daily learning goal is reached:



&#x20;   ┌─────────────────────────┐

&#x20;   │                         │

&#x20;   │      Session complete!  │

&#x20;   │                         │

&#x20;   │        +60 XP           │

&#x20;   │                         │

&#x20;   │     🔥 7 day streak     │

&#x20;   │                         │

&#x20;   │     8 cards completed   │

&#x20;   │                         │

&#x20;   │       \[ Done ]          │

&#x20;   │                         │

&#x20;   └─────────────────────────┘



The user can leave immediately or continue learning.



Reaching the daily goal should not prevent the learner from continuing.



\---



\## Navigation



&#x20;   Learn

&#x20;     ↓

&#x20;   Current Card

&#x20;     ↓

&#x20;   Answer / Continue

&#x20;     ↓

&#x20;   Feedback

&#x20;     ↓

&#x20;   Next Card

&#x20;     ↓

&#x20;   Session Complete



Topic switching:



&#x20;   Learn

&#x20;     ↓

&#x20;   Topic Switcher

&#x20;     ↓

&#x20;   My Learning

&#x20;     ↓

&#x20;   Selected Topic

&#x20;     ↓

&#x20;   That Topic's Feed



Bottom navigation:



&#x20;   Learn | Progress | You



\---



\## Loading State



Show a lightweight card skeleton while the next card is being prepared.



Do not show a blank screen.



Example:



&#x20;   ┌─────────────────────────┐

&#x20;   │                         │

&#x20;   │      ░░░░░░░░░░         │

&#x20;   │                         │

&#x20;   │   ░░░░░░░░░░░░░░░       │

&#x20;   │   ░░░░░░░░░░░░          │

&#x20;   │                         │

&#x20;   │        ░░░░░░░░         │

&#x20;   │                         │

&#x20;   └─────────────────────────┘



\---



\## Empty State



If there are no eligible cards:



> You're all caught up for now.



Actions:



\- `Review`

\- `Choose another topic`



Do not leave the learner on an unexplained blank screen.



\---



\## Error State



If the next card cannot be loaded:



> We couldn't load your next card.



Actions:



\- `Try Again`

\- `Back`



Previously completed progress must remain preserved.



\---



\## Wireframe Notes



The learning feed should remain visually focused.



Avoid:



\- Multiple cards visible simultaneously

\- Excessive statistics

\- Ads

\- Social content

\- Leaderboards

\- Long-form explanations

\- Unnecessary navigation controls



The primary action should always be obvious.



The learner should be able to complete a card with one clear interaction wherever possible.

