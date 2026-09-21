\# Wireframe 03 — Quiz Interaction \& Feedback



\## Goal



Give the learner a focused question, capture their answer, provide immediate useful feedback, and move them toward the next learning card.



The interaction should prioritize reasoning and learning over simply displaying whether an answer was correct.



\---



\## Screen — Quiz



\### Header



Elements:



\- Current topic

\- Card type: `QUIZ`

\- Session progress



Example:



&#x20;   Python · Quiz                         3/8



\### Question



Display one question at a time.



Example:



&#x20;   What does the following expression return?



&#x20;   len(\[10, 20, 30, 40])



\### Answer Options



Display a small set of clearly separated options.



Example:



&#x20;   ┌─────────────────────────────┐

&#x20;   │ A   3                       │

&#x20;   └─────────────────────────────┘



&#x20;   ┌─────────────────────────────┐

&#x20;   │ B   4                       │

&#x20;   └─────────────────────────────┘



&#x20;   ┌─────────────────────────────┐

&#x20;   │ C   10                      │

&#x20;   └─────────────────────────────┘



&#x20;   ┌─────────────────────────────┐

&#x20;   │ D   Error                   │

&#x20;   └─────────────────────────────┘



The learner selects one answer.



\---



\## Answer Selection



Before submission:



\- Selected option has a clear selected state.

\- Other options remain available until submission if the interaction design allows changing the answer.

\- Primary action becomes available after an answer is selected.



Primary action:



`Check Answer`



The learner should not accidentally submit an answer through an unrelated navigation action.



\---



\# Correct Answer Feedback



After submitting a correct answer:



&#x20;   ┌─────────────────────────────┐

&#x20;   │ ✓ Correct!                  │

&#x20;   │                             │

&#x20;   │ len() returns the number    │

&#x20;   │ of items in the sequence.   │

&#x20;   │                             │

&#x20;   │ +10 XP                      │

&#x20;   │                             │

&#x20;   │          \[ Continue ]       │

&#x20;   └─────────────────────────────┘



\### Elements



\- Correct indicator

\- Short explanation

\- XP earned

\- Continue button



The explanation should reinforce the underlying concept rather than simply repeat the answer.



\---



\# Incorrect Answer Feedback



After submitting an incorrect answer:



&#x20;   ┌─────────────────────────────┐

&#x20;   │ ✕ Not quite.                │

&#x20;   │                             │

&#x20;   │ The correct answer is B.    │

&#x20;   │                             │

&#x20;   │ len() returns the number    │

&#x20;   │ of items in the sequence.   │

&#x20;   │                             │

&#x20;   │          \[ Continue ]       │

&#x20;   └─────────────────────────────┘



\### Elements



\- Clear incorrect indicator

\- Correct answer

\- Short explanation

\- Continue button



Do not shame or punish the learner.



The feedback should explain the concept and allow the learner to continue.



\---



\# Feedback Rules



Feedback should:



\- Appear immediately after the answer

\- Clearly indicate whether the answer was correct

\- Explain why

\- Stay concise

\- Avoid unnecessary technical detail

\- Prepare the learner for the next card



The learner should understand the mistake before continuing.



\---



\# Adaptive Learning Interaction



The result of the quiz is recorded as part of the learner's card state.



Example:



&#x20;   Correct answer

&#x20;       ↓

&#x20;   Increase confidence/mastery

&#x20;       ↓

&#x20;   Schedule appropriate review

&#x20;       ↓

&#x20;   Continue progression



&#x20;   Incorrect answer

&#x20;       ↓

&#x20;   Decrease confidence/mastery

&#x20;       ↓

&#x20;   Schedule additional practice

&#x20;       ↓

&#x20;   Continue or revisit concept



The learner should not necessarily see the underlying mastery calculation.



\---



\# Spot the Bug Variant



The same interaction pattern is used for Spot the Bug cards.



Example:



&#x20;   Find the bug:



&#x20;   for (int i = 0; i <= 3; i++) {

&#x20;       printf("%d\\n", numbers\[i]);

&#x20;   }



Options:



&#x20;   A   printf cannot print integers



&#x20;   B   The loop accesses the array out of bounds



&#x20;   C   The array should start at index 1



&#x20;   D   There is no bug



After answering, show:



&#x20;   ✓ Correct!



&#x20;   The array contains three elements with

&#x20;   indexes 0, 1 and 2. When i becomes 3,

&#x20;   the program accesses the array out of bounds.



&#x20;   \[ Show Fixed Code ]



&#x20;   \[ Continue ]



The fixed code may be displayed when useful.



\---



\# Loading State



While submitting an answer:



\- Disable repeated submission

\- Keep the selected answer visible

\- Show a lightweight progress indicator



Do not clear the question.



\---



\# Error State



If the answer cannot be submitted:



> We couldn't save your answer.



Actions:



\- `Try Again`

\- `Continue Offline` only if offline support is explicitly implemented later



For the initial pilot, retrying is sufficient.



The learner's previous completed cards must remain preserved.



\---



\# Navigation



Normal quiz flow:



&#x20;   Quiz

&#x20;     ↓

&#x20;   Select Answer

&#x20;     ↓

&#x20;   Check Answer

&#x20;     ↓

&#x20;   Feedback

&#x20;     ↓

&#x20;   Continue

&#x20;     ↓

&#x20;   Next Card



Exit:



&#x20;   Quiz

&#x20;     ↓

&#x20;   Pause / Exit

&#x20;     ↓

&#x20;   Learning Feed / Home



\---



\# Wireframe Notes



The feedback screen should not become a second lesson.



Keep explanations short enough to read within the normal card time.



Avoid:



\- Long paragraphs

\- Immediate answer changes after selection

\- Multiple questions on one screen

\- Punishing incorrect answers

\- Excessive animations

\- Leaderboards or social comparison



The learner should leave each question knowing a little more than they did before answering it.

