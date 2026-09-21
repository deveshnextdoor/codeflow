# CodeFlow — Pilot Metrics

## Purpose

The pilot should determine whether CodeFlow can create short, repeatable learning sessions that improve users' understanding and retention of programming concepts.

The pilot is exploratory. With approximately 12–50 users, results should be treated as directional evidence rather than statistically strong proof.

## Primary Metrics

### 1. Quiz Accuracy Over Time

**Definition:**

`correct quiz attempts / total quiz attempts × 100`

Track accuracy for each user and concept over repeated exposure.

For the delayed-accuracy analysis, each concept should have at least 3 quiz cards. One quiz card is held out as a **delayed check** and is never used for practice. The remaining quiz cards can be used during learning and practice.

**Hypothesis:**

Users improve by at least **15 percentage points** between first exposure and later assessment of the same concept.

**Limitation:**

Repeated questions can measure familiarity rather than genuine transfer of knowledge. Use the held-out delayed-check question so the delayed assessment is not a question previously used for practice.

---

### 2. D1 Retention

**Definition:**

Percentage of users who complete at least one learning card on the calendar day after their first-session day, using the user's local time.

`D1 = users active on the calendar day after first-session day / users with a completed first session × 100`

**Hypothesis:** ≥ **30%**

---

### 3. D7 Retention

**Definition:**

Percentage of users who complete at least one learning card on the seventh calendar day after their first-session day, using the user's local time.

`D7 = users active on day 7 / users with a completed first session × 100`

**Hypothesis:** ≥ **15%**

Also report:

**Returned within 7 days:** percentage of users who complete at least one learning card on any calendar day within the seven days following their first-session day.

This is a secondary retention metric and does not replace D1 or D7.

---

### 4. Session Length

**Definition:**

Time between the beginning and end of a learning session.

Sessions are separated after **5 minutes of inactivity**.

**Hypothesis:**

Median session length is approximately **5–10 minutes**.

The goal is to validate that CodeFlow supports meaningful short sessions rather than requiring long study periods.

---

### 5. Cards per Session

**Definition:**

Number of cards completed during each learning session.

**Hypothesis:**

Median session contains approximately **5–12 completed cards**.

Track median and distribution rather than relying only on the mean.

---

## Adaptive vs Random Experiment

### Purpose

Determine whether adaptive card selection improves delayed learning compared with random selection.

### Design

The primary experiment is a **within-user paired comparison assigned at the Concept level**.

Each user's Concepts within a Topic are divided into two balanced groups:

- **Adaptive-practiced Concepts**
- **Random-practiced Concepts**

Assignment should use:

- a seeded shuffle
- alternating adaptive/random assignment
- a random starting policy for each user

The assignment is made once per Concept rather than independently for each card or practice slot. This keeps the practice policy stable for a Concept and reduces contamination between the two conditions.

Store the assigned policy as `UserConceptMastery.practice_policy`.

### Practice Policies

**Adaptive:**

Cards within the assigned Concept are selected using the learner's performance and mastery state.

**Random:**

Cards within the assigned Concept are selected randomly from the eligible practice pool.

The underlying content structure should be equivalent across the two conditions.

### Delayed Check

Each Concept should have one quiz card designated as the **delayed check**.

The delayed-check card:

- is not used for practice
- is not selected by the adaptive policy
- is not selected by the random policy
- is used to measure delayed quiz accuracy for that Concept

This ensures the delayed assessment uses a question that the learner has not practiced directly.

### Primary Outcome

The primary outcome is the **per-user difference in delayed quiz accuracy** between adaptive-practiced and random-practiced Concepts.

For each user:

`paired difference = delayed accuracy on adaptive-practiced Concepts − delayed accuracy on random-practiced Concepts`

Report:

- raw adaptive delayed accuracy
- raw random delayed accuracy
- per-user paired differences
- aggregate paired difference

The result should be reported as **directional, not conclusive**, given the small pilot size.

### Hypothesis

Adaptive practice produces a higher delayed quiz accuracy than random practice on the same user's assigned Concepts.

The original 10 percentage-point hypothesis remains an exploratory target rather than a claim of expected statistical significance.

### Secondary Outcomes

Compare:

- Immediate quiz accuracy
- Cards completed
- Session length
- Return rate

These are supporting product and learning signals, not additional experimental designs.

## What the Pilot Can and Cannot Prove

### It can provide evidence about:

- Whether users understand and use the core learning loop
- Whether users return after their first session
- Whether short sessions are practical
- Whether adaptive selection appears useful compared with random selection
- Which content types users struggle with
- Whether users remember concepts, reason about code and spot bugs better over time

### It cannot reliably establish:

- General effectiveness for the entire population
- Long-term learning outcomes
- Superiority over established educational products
- Statistically robust adaptive-learning effects
- Causal conclusions from very small samples

Results should therefore be reported with sample size, group size, completion rates, raw outcome numbers, and uncertainty rather than presenting small differences as definitive findings.

## Pilot Principle

**Optimize for learning evidence, not engagement vanity metrics.**

XP, streaks and cards completed are useful product signals, but the central question is whether users can **remember concepts, reason about code and spot bugs better over time.**