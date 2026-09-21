CodeFlow — Data Model

Purpose

The data model describes what CodeFlow needs to remember about users, learning content, attempts, mastery, review state, gamification and product events.

The model is intentionally small for the pilot. It should support independent progress across learning topics, adaptive practice and the pilot metrics without introducing a full course-management hierarchy.

For the V1 pilot, Python and C are the seed topics. C++ is a stretch topic. Topic.language is plain text and language-agnostic, so C++ can be added later as data without changing the schema.

Core Entities

User

Represents a learner.

v0.x fields:

id — client-generated UUID created at first launch

auth_uid — nullable; filled when the user logs in in Phase 7

created_at

daily_goal_minutes

current_topic_id

total_xp

current_streak

The client-generated id allows attempts and events created before login to remain associated with the same user after authentication.

Topic

Represents a selectable learning path such as Python or C.

v0.x fields:

id

name

description

language — plain text, not an enum or hard-coded list

status

V1 pilot seed topics:

Python

C

Stretch topic:

C++

Each topic has independent learner progress.

C++ can be added later as a new Topic row without changing the schema.

Concept

Represents a teachable concept within a Topic.

v0.x fields:

id

topic_id

name

description

order_index

Examples:

Python → Variables

Python → Conditions

C → Variables

C → Loops

A Concept belongs to exactly one Topic.

Card

Represents an individual learning or practice unit.

v0.x fields:

id

concept_id

type

title

content

difficulty

estimated_seconds

Every Card belongs to exactly one Concept.

The Topic for a Card is derived through its Concept rather than stored redundantly on the Card.

V1 card types:

Concept — short explanation of one idea

Code — read and reason about code

Quiz — test recall and understanding

Spot the Bug — identify and reason about programming errors

Prerequisite

Represents a prerequisite relationship between Concepts.

v0.x fields:

concept_id

prerequisite_concept_id

In V1, prerequisite links must connect Concepts within the same Topic.

Example:

Python Variables
↓
Python Conditions
↓
Python Loops
↓
Python Functions

The model intentionally does not introduce a full course/module hierarchy yet.

Attempt

Represents one user attempt on a Card.

v0.x fields:

id

user_id

card_id

answered_at

is_correct

response_time_ms

session_id

selection_policy

selection_policy identifies why the Card was selected:

curriculum

adaptive

random

review

This is required so the adaptive-vs-random experiment can be analysed later.

UserCardState

Stores the learner's current state for an individual Card.

v0.x fields:

user_id

card_id

mastery

last_seen_at

next_review_at

correct_count

incorrect_count

consecutive_correct

This supports adaptive practice and basic spaced review.

UserConceptMastery

Stores the learner's mastery of a Concept.

v0.x fields:

user_id

concept_id

mastery — 0 to 1

status — not_started, learning, or mastered

last_activity

Topic progress percentage is derived from the mastery state of the Concepts belonging to that Topic.

UserTopicMastery

Stores topic-level progress as an optional cached representation.

Later / optional:

user_id

topic_id

mastery

cards_completed

concepts_mastered

last_active_at

The source of truth for concept-level mastery is UserConceptMastery. UserTopicMastery may be introduced later as a cache or convenience layer if deriving topic progress becomes expensive or frequently required.

XP / Streak

Stores gamification state.

v0.x fields:

total XP

current streak

The exact implementation can remain small during the pilot.

Event

Records important product and learning events.

v0.x fields:

id

user_id

event_type

timestamp

topic_id

card_id

session_id

metadata

Important events include:

session started

session completed

card viewed

card completed

quiz answered

bug answered

topic selected

topic switched

Events should be recorded from the beginning so pilot behaviour can be analysed without reconstructing activity later.

Relationships

erDiagram
    USER ||--o{ ATTEMPT : makes
    USER ||--o{ USER_CARD_STATE : has
    USER ||--o{ USER_CONCEPT_MASTERY : has
    USER ||--o{ USER_TOPIC_MASTERY : may_have
    USER ||--o{ EVENT : generates

    TOPIC ||--o{ CONCEPT : contains
    CONCEPT ||--o{ CARD : contains

    CONCEPT ||--o{ PREREQUISITE : requires
    CONCEPT ||--o{ PREREQUISITE : is_required_by

    CARD ||--o{ ATTEMPT : receives
    CARD ||--o{ USER_CARD_STATE : tracked_by

    TOPIC ||--o{ USER_TOPIC_MASTERY : tracked_by
    CONCEPT ||--o{ USER_CONCEPT_MASTERY : tracked_by

    TOPIC ||--o{ EVENT : referenced_by
    CARD ||--o{ EVENT : referenced_by

    USER {
        uuid id PK
        string auth_uid
        datetime created_at
        int daily_goal_minutes
        uuid current_topic_id
        int total_xp
        int current_streak
    }

    TOPIC {
        uuid id PK
        string name
        string description
        string language
        string status
    }

    CONCEPT {
        uuid id PK
        uuid topic_id FK
        string name
        string description
        int order_index
    }

    CARD {
        uuid id PK
        uuid concept_id FK
        string type
        string title
        text content
        string difficulty
        int estimated_seconds
    }

    PREREQUISITE {
        uuid concept_id FK
        uuid prerequisite_concept_id FK
    }

    ATTEMPT {
        uuid id PK
        uuid user_id FK
        uuid card_id FK
        datetime answered_at
        boolean is_correct
        int response_time_ms
        string session_id
        string selection_policy
    }

    USER_CARD_STATE {
        uuid user_id FK
        uuid card_id FK
        float mastery
        datetime last_seen_at
        datetime next_review_at
        int correct_count
        int incorrect_count
        int consecutive_correct
    }

    USER_CONCEPT_MASTERY {
        uuid user_id FK
        uuid concept_id FK
        float mastery
        string status
        datetime last_activity
    }

    USER_TOPIC_MASTERY {
        uuid user_id FK
        uuid topic_id FK
        float mastery
        int cards_completed
        int concepts_mastered
        datetime last_active_at
    }

    EVENT {
        uuid id PK
        uuid user_id FK
        string event_type
        datetime timestamp
        uuid topic_id FK
        uuid card_id FK
        string session_id
        json metadata
    }

v0.x vs Later

v0.x

The pilot data model should support:

User

Topic

Concept

Card

Prerequisite

Attempt

UserCardState

UserConceptMastery

XP/streak

Event

independent progress by Topic

curriculum, adaptive, random and review selection policies

basic spaced review

pilot metrics

Later

The following are intentionally deferred:

Course → Module → Concept hierarchy

Optional cached UserTopicMastery implementation

Achievements

Leaderboards

Social features

User-generated content

Advanced recommendation models

AI-generated content

AI tutor/RAG

richer analytics models

The schema should remain small until the pilot demonstrates that additional structure is necessary.