\# Wireframe — Progress



\## Goal



Help users understand what they have learned, what they are improving, and how their mastery is changing over time.



The screen should reinforce learning progress rather than simply showing completion statistics.



\---



\## Navigation



Bottom navigation:



\- Learn

\- Progress

\- You



Progress is the active tab.



\---



\## Screen — Progress Overview



\### Header



\- Title: Progress

\- Optional date range: This week / All time



\### Topic mastery



Show each saved topic independently.



Example:



\- Python — 72% mastery

\- C — 41% mastery

\- C++ — 18% mastery



Each topic can show:



\- mastery percentage

\- concepts mastered

\- cards completed

\- last active



Selecting a topic opens its detailed progress.



\---



\## Learning Performance



Show a small summary of learning performance.



Example:



\### Understanding



\- Quiz accuracy: 78%



\### Problem solving



\- Problems solved: 24

\- Bug-fixing accuracy: 71%



\### Review



\- Due for review: 6 cards



Keep these numbers understandable and avoid creating a dashboard full of statistics.



\---



\## Streak



Show:



\- Current streak

\- Longest streak

\- Recent activity



Example:



> 🔥 6 day streak



The streak should encourage consistency but should not dominate the screen.



\---



\## Topic Detail



When a user selects a topic:



\### Python



Mastery: 72%



Progress sections:



\- Variables — Mastered

\- Conditions — Mastered

\- Loops — Learning

\- Functions — Learning

\- Collections — Not started

\- Problem Solving — Not started



Each concept can show:



\- mastery

\- review status

\- number of attempts

\- recent accuracy



\---



\## Review State



If cards are due for review:



> You have 6 concepts ready for review.



Primary action:



\*\*Review now\*\*



Review should take the user into the normal learning/card flow rather than creating a separate learning system.



\---



\## Empty State



If the user has not completed enough learning yet:



> Your progress will appear here as you learn.



Primary action:



\*\*Start learning\*\*



\---



\## Loading State



Show lightweight placeholders for:



\- topic mastery

\- learning performance

\- streak

\- recent activity



Do not block the entire screen unnecessarily.



\---



\## Error State



If progress cannot be loaded:



> We couldn't load your progress.



Actions:



\- Retry

\- Continue learning



Previously recorded learning progress should not be deleted because of a temporary loading error.



\---



\## Topic Switching



Users can have progress in multiple topics.



Example:



Python — 72%  

C — 41%  

C++ — 18%



Switching the current learning topic must never reset progress.



Each topic keeps its own:



\- mastery

\- completed cards

\- attempts

\- review schedule

\- learning history



\---



\## Wireframe Notes



Keep the screen:



\- simple

\- readable

\- progress-focused

\- useful at a glance



Avoid:



\- complicated charts

\- excessive statistics

\- competitive rankings

\- leaderboards

\- social comparisons

\- badges taking over the screen

\- fake precision

\- overwhelming analytics

