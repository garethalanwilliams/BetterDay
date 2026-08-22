BetterDay

BetterDay is a lightweight personal health and recovery prototype
designed to learn from a person’s own patterns over time.

The product combines simple daily logging with recovery context and, in
later iterations, AI-assisted interpretation of trends and personalised
recommendations. The core principle is that deterministic rules protect
data quality and evidence handling, while AI does the heavier
interpretation, synthesis and recommendation selection.

##Current prototype

Version: v3.3.1

Current focus: Learning Data Foundation

The prototype currently supports:

-   Morning check-in: sleep duration, sleep quality and 1–10 subjective
    feeling
-   Optional HRV and resting-heart-rate inputs against personal recent
    baselines
-   Planned movement and actual movement outcome
-   Natural-language food logging with prototype NOVA classification
-   One-tap hydration logging
-   Explicit alcohol logging
-   Daily recovery interpretation
-   Today focus/recommendation
-   Insights and weekly-review prototype flows
-   Test scenarios for clean start, historical days and poor recovery
-   Developer/test views for Daily Observation and Recovery Observation
    JSON

Product principles

-   Unknown data is not treated as bad, zero or complete.
-   Today is kept separate from historical data.
-   HRV and resting heart rate are interpreted against the user’s own
    recent baseline, not population targets.
-   Observational relationships are not presented as proof of causation.
-   BetterDay should select one useful primary recommendation rather
    than overwhelm the user.
-   It is valid for BetterDay to recommend maintaining the current
    balance when nothing needs changing.
-   The product should become more intelligent without becoming a larger
    daily questionnaire.

Learning Engine direction

The planned Learning Engine follows this flow:

    Raw logs / wearable data
            ↓
    Daily Observation
            ↓
    Recovery Observation
            ↓
    Comparable evidence
            ↓
    Candidate trends
            ↓
    Evidence confidence
            ↓
    AI interpretation
            ↓
    Today's Focus / Insight / Weekly Recommendation
            ↓
    Recommendation history and future learning

Deterministic code is responsible for missing-data handling, observation
counts, basic trend calculations, consistency, magnitude and confidence
gates.

AI is intended to handle interpretation, confounder-aware synthesis,
deciding what is useful enough to surface, and choosing the single most
useful recommendation.

Current development path

    v3.2  Stable prototype baseline
    v3.3  Learning Data Foundation
    v3.3.1 Regression patch
    v3.4  Candidate trend / evidence engine
    v4.x  AI reasoning integration

Testing

Use the ••• test menu in the prototype for:

-   Day 1 — clean start
-   Day 4 — historical-data test
-   Day 8 — first-review test
-   Poor recovery test
-   Reset all data
-   Daily Observation JSON
-   Recovery Observation JSON

The visible version number in this menu should be used when reporting
test screenshots or defects.

Project files

-   index.html — current prototype
-   README.md — project overview
-   BACKLOG.md — prioritised development and regression backlog

Detailed Learning Engine design documents and JSON schemas are
maintained separately and should move into a docs/ area as
implementation progresses.
