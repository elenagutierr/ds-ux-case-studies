# UX / Data Science Research Decision Memo 
## Retrospective causal event study: How experience changes decision strategy 

**Role**: Research lead (study framing and design, data collection, modelling approach, analysis, insight narrative)  
**Methods**: Retrospective analysis, quasi-experimental event study, longitudinal modelling, model comparison (BIC/Schwarz weights)  
**What this shows**: How I turn longitudinal behavioural data into causal hypotheses, quantify mechanism change over time, and translate it into product-style recommendations.

---

## 1) Problem Framing and Decision to make  
When user behaviour improves over time, teams often ask:  
**Is this improvement driven by the product change itself, or by users learning and adapting (e.g. change aversion, novelty effects)?**

*Decision this analysis supports*: 
When introducing a new but structurally similar workflow (a “set switch”), should we expect users to *transfer* prior learning (fast adoption), or do they *reset* and require fresh onboarding and support?

*Industry relevance*:  
This maps to feature rollouts where performance shifts could reflect **adoption/learning** rather than the inherent quality of the change, so we need a design and measurement strategy that separates the two.  

---

## 2) Research questions
1. **Transfer**: Does prior exposure to the problem structure facilitate user response immediately when a new, similar problem set is introduced?
2. **Mechanism**: Does the decision strategy itself change with experience (not just performance)?
3. **Acceleration**: Does strategy convergence become faster across successive problem switches (evidence of generalisation)?

---

## 3) Hypotheses 
- Early performance after a new problem switch will be better than early performance in the first problem set.
- With experience, behaviour will shift from a simpler heuristic strategy toward a more optimal strategy.
- Strategy convergence after a switch will become faster across successive switches (evidence of “learning how to learn”).

---

## 3) Why a retrospective causal (event study) approach
Randomised experiments aren’t always possible for questions related to experience and learning. This project used two quasi-experimental levers that are common in industry analytics:
- **Within-subject longitudinal data**: track the same users across repeated sessions.
- **Exogenous “event” (set switch)**: introducing a new problem set creates a discrete change in environment that can be analysed like a rollout or workflow change.

This supports *causal hypothesis testing* (not “proof”), by checking whether outcomes shift sharply at events, whether trajectories differ pre/post, and whether effects strengthen with accumulated experience.

---

## 4) Data & design (high level)
Subjects completed repeated value-based choices across many sessions. The environment changed in discrete blocks via **problem set switches** (analogous to “new workflow introduced”).  

**Key comparison windows**:
- Early sessions on Set 1 vs early sessions on Set 2 (transfer at first exposure to novelty)
- Strategy trajectories across sessions and across multiple set switches (acceleration with experience)

---

## 5) Metrics
### Primary outcomes
- **Performance sensitivity** to value differences (psychometric slope; “discrimination”)
- **Choice consistency and accuracy**

### Mechanism metrics 
A model-based “strategy index” captured whether decisions followed:
- **Additive integration** (simple heuristic)
- **Multiplicative integration** (near-optimal)

### Guardrails
- Pre-trend checks (no sharp changes before the switch)
- Robustness across alternative model specs

---

## 6) What we learned
### What changed at the event (transfer)
Early performance was better on the new problem set than at the start of the first set, consistent with transferable learning.

### What changed over time (mechanism shift)
Model fits indicated decision strategy evolved with experience: behaviour moved away from simple heuristics toward a near-optimal strategy.

### What changed across repeated events (acceleration)
After successive problem set switches, convergence to the optimal strategy happened earlier. This suggests experience reduces the “reset cost” of novelty.

---

## 8) Interpretation
This pattern supports a product-relevant mechanism:
- When the environment changes (“new workflow”), users initially experience uncertainty and may revert to simpler heuristics.
- With accumulated exposure, users learn *how to learn* the problem structure, leading to faster re-convergence on the optimal strategy after each change.

In industry terms: users build **transferable mental models**, and the cost of change decreases as familiarity with the broader system grows.

---

## 9) Actionable next steps
If this were a developer tool or enterprise workflow rollout, I would apply these learnings as follows:

1. **Design for the “switch moment”**
   - Users may temporarily revert to simple heuristics right after a workflow change.
   - Add lightweight guidance that reduces uncertainty (clear feedback, “what changed” cues, shortcuts).

2. **Measure adoption as mechanism, not only outcomes**
   - Track behavioural proxies for “optimal strategy adoption” (e.g., fewer retries, fewer backtracks, reduced time in logs, fewer support pings).
   - Pair outcome metrics (speed, success rate) with mechanism metrics (path efficiency, error recovery patterns).

3. **Expect faster recovery for experienced users; support novices differently**
   - Segment by experience level and tailor onboarding/help accordingly.
   - Evaluate rollouts with an event-study lens to avoid mistaking learning effects for product impact.

---

## 10) Limitations 
- This is a **quasi-experimental** causal design: set switches act like interventions, but not all confounds can be eliminated.
- Model-based inference is interpretive; I used model comparison (BIC/Schwarz weights) and longitudinal consistency checks to reduce overfitting and increase robustness. 



