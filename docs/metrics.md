\# CodeFlow — Pilot Metrics



\## Purpose



The pilot should determine whether CodeFlow can create short, repeatable learning sessions that improve users' understanding and retention of programming concepts.



The pilot is exploratory. With approximately 12–50 users, results should be treated as directional evidence rather than statistically strong proof.



\## Primary Metrics



\### 1. Quiz Accuracy Over Time



\*\*Definition:\*\*



`correct quiz attempts / total quiz attempts × 100`



Track accuracy for each user and concept over repeated exposure.



\*\*Hypothesis:\*\*



Users improve by at least \*\*15 percentage points\*\* between first exposure and later assessment of the same concept.



\*\*Limitation:\*\* Repeated questions can measure familiarity rather than genuine transfer of knowledge. Use different questions testing the same concept where possible.



\---



\### 2. D1 Retention



\*\*Definition:\*\*



Percentage of users who complete at least one learning card on the calendar day after their first completed session.



`D1 = users active on day 1 / users with completed first session × 100`



\*\*Hypothesis:\*\* ≥ \*\*30%\*\*



\---



\### 3. D7 Retention



\*\*Definition:\*\*



Percentage of users who complete at least one learning card on the seventh calendar day after their first completed session.



`D7 = users active on day 7 / users with completed first session × 100`



\*\*Hypothesis:\*\* ≥ \*\*15%\*\*



\---



\### 4. Session Length



\*\*Definition:\*\*



Time between the beginning and end of a learning session.



Sessions are separated after \*\*5 minutes of inactivity\*\*.



\*\*Hypothesis:\*\*



Median session length is approximately \*\*5–10 minutes\*\*.



The goal is to validate that CodeFlow supports meaningful short sessions rather than requiring long study periods.



\---



\### 5. Cards per Session



\*\*Definition:\*\*



Number of cards completed during each learning session.



\*\*Hypothesis:\*\*



Median session contains approximately \*\*5–12 completed cards\*\*.



Track median and distribution rather than relying only on the mean.



\---



\## Adaptive vs Random Experiment



\### Purpose



Determine whether adaptive card selection improves learning compared with random selection.



\### Groups



\*\*Adaptive:\*\* cards selected using user performance/mastery.



\*\*Random:\*\* cards selected randomly from the same eligible content pool.



\### Primary Outcome



Delayed quiz accuracy on the same underlying concepts.



`Adaptive accuracy − Random accuracy`



\### Hypothesis



Adaptive selection produces at least a \*\*10 percentage-point improvement\*\* in delayed quiz accuracy.



\### Secondary Outcomes



Compare:



\- Immediate quiz accuracy

\- Delayed quiz accuracy

\- Cards completed

\- Session length

\- Return rate



\## What the Pilot Can and Cannot Prove



\### It can provide evidence about:



\- Whether users understand and use the core learning loop

\- Whether users return after their first session

\- Whether short sessions are practical

\- Whether adaptive selection appears more useful than random selection

\- Which content types users struggle with



\### It cannot reliably establish:



\- General effectiveness for the entire population

\- Long-term learning outcomes

\- Superiority over established educational products

\- Statistically robust adaptive-learning effects

\- Causal conclusions from very small samples



Results should therefore be reported with sample size, group size, completion rates, and uncertainty rather than presenting small differences as definitive findings.



\## Pilot Principle



\*\*Optimize for learning evidence, not engagement vanity metrics.\*\*



XP, streaks and cards completed are useful product signals, but the central question is whether users can \*\*remember concepts and solve problems better over time.\*\*

