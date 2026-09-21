\# Wireframe 01 — Onboarding



\## Goal



Get a new learner into their first learning session with minimal setup.



Onboarding should answer:



1\. What is CodeFlow?

2\. What do you want to learn?

3\. How comfortable are you?

4\. How much time do you want to spend daily?



The first selected topic becomes the user's current learning path. Users can add or switch learning paths later without losing progress.



\---



\## Screen 1 — Welcome



\### Elements



\- CodeFlow logo/name

\- Short value proposition:

&#x20; - "Learn CS a little every day."

\- Supporting message:

&#x20; - "Understand → Practice → Solve → Remember"

\- Primary button: `Get Started`

\- Optional secondary action: `Skip`



\### Actions



\*\*Get Started\*\*



→ Topic Selection



\*\*Skip\*\*



→ Topic Selection



For the pilot, skipping should not bypass topic selection.



\### Loading



Not expected.



\### Empty



Not applicable.



\### Error



Not expected.



\---



\## Screen 2 — Choose Your First Topic



\### Elements



Title:



> What do you want to learn?



Topic cards:



\- Python

\- C

\- C++



Supporting text:



> You can change or add learning paths later.



Primary button:



`Continue`



\### Interaction



User selects exactly one topic for the initial path.



Selected topic has a clear visual state.



\### Actions



\*\*Continue\*\*



→ Level Selection



No topic selected:



`Continue` remains disabled.



\### Loading



Show topic placeholders if topic metadata is being loaded.



\### Empty



> No learning paths are available right now.



Provide a retry action.



\### Error



> We couldn't load the learning paths.



Actions:



\- `Retry`



\---



\## Screen 3 — Choose Your Level



\### Elements



Title:



> How comfortable are you?



Options:



\- I'm completely new

\- I've seen some basics

\- I can write simple programs

\- I'm comfortable coding



Use descriptive options rather than labels such as Beginner / Intermediate / Advanced.



\### Actions



Selecting an option enables:



`Continue`



\*\*Continue\*\*



→ Daily Goal



\### Loading



Not expected after topic selection.



\### Empty



Not applicable.



\### Error



Not expected.



\---



\## Screen 4 — Daily Goal



\### Elements



Title:



> How much time do you have?



Options:



\### 5 minutes



Quick daily practice



\### 10 minutes



Standard session



\### 15 minutes



Deeper practice



Recommended/default selection:



`10 minutes`



Supporting text:



> This is a daily target, not a minimum requirement.



\### Actions



Selecting a goal enables:



`Start Learning`



\*\*Start Learning\*\*



→ Learning Feed



The selected topic becomes the current learning path.



\### Loading



Show a short transition/loading state while the first learning session is prepared.



\### Empty



If no cards are available:



> This learning path isn't ready yet.



Actions:



\- `Choose another topic`

\- `Try again`



\### Error



> We couldn't prepare your learning session.



Action:



`Try Again`



\---



\# Post-Onboarding Topic Switching



Onboarding creates the learner's first learning path, but does not permanently lock them into it.



Later, users can open their learning-path selector and:



\- Add another topic

\- Switch the current topic

\- Return to a previously paused topic



Example:



```text

My Learning



Python

███████░░░ 72%

Continue →



C

████░░░░░░ 41%

Continue →



C++

██░░░░░░░░ 18%

Continue →

Switching topics must preserve the previous topic's:

Progress
Mastery
Attempts
Review state
Learning history
Navigation Flow
Welcome
   ↓
Choose Topic
   ↓
Choose Level
   ↓
Daily Goal
   ↓
Learning Feed

After onboarding:

Learning Feed
      ↓
  Switch Topic
      ↓
  My Learning
   ↙   ↓   ↘
Python  C   C++

# Wireframe Notes

The onboarding should feel lightweight.

Avoid:

- Long explanations
- Account/profile customization
- Social setup
- Complex preferences
- Multiple configuration screens
- Asking for information that is not needed for the learning experience