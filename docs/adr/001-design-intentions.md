# ADR-001: Design Intentions Layer System

**Status:** Proposed
**Date:** 2026-01-30

## Context

The current token system provides a single set of values. However, optimal interface design varies significantly based on the cognitive demands of the task and the decision-making context.

### Cognitive load and decision-making

**Dual Process Theory** (Kahneman, 2011) distinguishes between:

- **System 1**: Fast, automatic, intuitive processing
- **System 2**: Slow, deliberate, analytical processing

Interface design either supports or hinders these processes. High-stakes environments require sustained System 2 engagement with minimal System 1 interference. Consumer contexts often benefit from System 1 heuristics (social proof, aesthetic appeal).

**Hick-Hyman Law** states decision time increases logarithmically with the number of choices. Information-dense interfaces in expert domains work because trained users have chunked options into recognizable patterns, reducing effective choice count.

**Signal Detection Theory** applies to monitoring tasks. Users must discriminate signals (actionable events) from noise (background state). Design choices affect both sensitivity (d') and response bias (β):

- Visual clutter reduces sensitivity
- Unnecessary salience causes false alarms
- Muted baselines allow true signals to reach threshold

### Trust calibration

Trust in human-computer interaction is calibrated through learned associations (Lee & See, 2004). Users develop expectations about system behavior and evaluate trustworthiness through:

- **Performance** - Does the system do what it claims?
- **Process** - Can I understand how it operates?
- **Purpose** - Do I believe it serves my interests?

Visual design functions as a trust signal. These signals are domain-specific:

**High-stakes decision environments** (trading, medical, operations)

Users maintain vigilance over extended periods, making rapid decisions with significant consequences. Cognitive requirements:

- Sustained attention with low signal frequency
- Rapid pattern recognition in trained experts
- Minimized extraneous cognitive load
- High sensitivity to state changes

Trust signals:
- Information density supports expert mental models
- Temporal stability (minimal motion) preserves attentional resources
- Precision typography enables rapid numerical comparison
- Muted chromatic baseline allows deviation-based alerting
- Immediate feedback confirms system responsiveness
- Aesthetic restraint signals prioritization of function

Distrust triggers: Animation, high chroma, decorative elements—associated with persuasion and manipulation contexts.

**Evaluative/consumer contexts** (marketing, onboarding)

Users assess whether to engage, allocating limited attention across competing options. Cognitive requirements:

- Rapid credibility assessment (often < 50ms for first impression)
- Heuristic-based evaluation under uncertainty
- Emotional engagement to drive action

Trust signals:
- Production value indicates resource investment (costly signaling)
- Whitespace signals confidence, reduces perceived desperation
- Motion demonstrates technical competence and modernity
- Consistent brand identity enables recognition and recall
- Social proof reduces uncertainty through conformity heuristics

Distrust triggers: Information overload, clinical aesthetics, or excessive polish without substance (uncanny valley of marketing).

### The problem

A single token set optimizes for one cognitive context at the expense of others. Applying consumer-context aesthetics to expert decision interfaces increases cognitive load and triggers learned distrust associations. Applying expert-context minimalism to consumer interfaces fails credibility heuristics.

## Decision

Introduce a **Design Intentions** layer with three variants optimized for distinct cognitive demands:

| Intention | Cognitive optimization | Decision context |
|-----------|------------------------|------------------|
| **Expressive** | System 1 heuristics, credibility signaling | Evaluation, persuasion, engagement |
| **Focus** | Balanced load, sustained productivity | Knowledge work, task completion |
| **Intense** | Expert System 2, signal detection | High-stakes, time-critical, monitoring |

### Token calibration by intention

| Category | Expressive | Focus | Intense |
|----------|------------|-------|---------|
| **Motion** | Present, emphasized easing, longer duration | Functional, standard easing | Minimal or absent |
| **Spacing** | Generous, supports visual hierarchy | Balanced | Dense, maximizes information |
| **Radius** | Soft, approachable geometry | Moderate | Sharp, precise boundaries |
| **Typography** | Proportional, relaxed metrics | Balanced | Tabular figures, tight leading, monospace options |
| **Color** | Higher chroma, expressive range | Moderate saturation | Low saturation baseline, reserved high-contrast for alerts |
| **Information density** | Low, focused attention | Moderate | High, supports pattern recognition |

### Design principles by intention

**Expressive**
- Leverages aesthetic-usability effect (attractive things perceived as easier to use)
- Motion provides feedback and demonstrates system capability
- Whitespace and hierarchy guide attention through intended flow
- Optimized for first impressions and credibility assessment

**Focus**
- Reduces extraneous cognitive load while maintaining engagement
- Consistent rhythm supports scanning and task flow
- Balances information access with visual clarity
- Optimized for sustained productive sessions

**Intense**
- Minimizes cognitive load unrelated to primary task
- Supports preattentive processing for anomaly detection
- Maximizes signal-to-noise ratio in visual field
- Preserves attentional resources for decision-making
- Deliberately eschews aesthetic elements associated with persuasion contexts

## Consequences

### Positive

- Design decisions grounded in cognitive science rather than aesthetic preference
- Clear guidance for domain-appropriate optimization
- Enables contextual mixing (e.g., intense data views within focus application shell)
- Makes implicit expertise explicit and transferable

### Negative

- Three coordinated token sets to maintain
- Requires understanding of cognitive context to apply correctly
- Misapplication actively degrades performance and trust

### Neutral

- Base tokens remain unchanged
- Users can compose manually without using intentions

## References

- Kahneman, D. (2011). Thinking, Fast and Slow
- Lee, J. D., & See, K. A. (2004). Trust in Automation: Designing for Appropriate Reliance
- Hick, W. E. (1952). On the Rate of Gain of Information
- Wickens, C. D. (2008). Multiple Resources and Mental Workload
- Lindgaard, G., et al. (2006). Attention Web Designers: You Have 50 Milliseconds to Make a Good First Impression

## Open Questions

- [ ] Should intentions be mutually exclusive or composable per-region?
- [ ] How do intentions interact with color palettes (semantic vs chromatic)?
- [ ] Implementation: data attributes vs CSS files vs custom property presets?
- [ ] How do we validate intention effectiveness empirically?
- [ ] What transition handling is needed when switching intentions?
