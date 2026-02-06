# UX / Data Science Research Decision Memo 
## Remote A/B-style Experiment: Do incentives change information retention?

**Role**: Study lead (study design, remote implementation, analysis, insight readout)  
**Setting**: Fully remote (recruitment + delivery via online platforms)  
**Methods**: Controlled experiment (A/B-style manipulation), remote testing, behavioural metrics, data-quality screening  
**What this shows**: How I frame a problem, choose methods, design for data quality, and translate results into decisions and next steps.

## 1) Problem Framing and Decision to make
When people repeat a task, they often get faster as they implicitly learn patterns. I wanted to test whether **explicit incentives** (high vs low monetary reward) can **accelerate that learning** and measurably change performance.

*Decision this research supports*:  
Should we invest in incentive mechanics as a reliable lever for changing behaviour in a remote setting, or focus on simplifying the experience first?

*Industry relevance*:  
This is the same decision teams face when adding incentives (credits, pricing prompts, nudges): **do rewards create sustained behaviour change, and what's the least risky way to test this remotely?**

---

## 2) Research questions
1. **Primary**: Does associating specific repeating patterns with **high reward vs low reward** lead to faster information detection?
2. **Feasibility**: Can a complex effect replicate **online** with acceptable data quality?
3. **Experience risk**: Does adding reward (and the UX required to communicate it) increase cognitive load and undermine the effect online?

---

## 3) Hypotheses 
- High-reward patterns are detected faster than low-reward patterns after only a small number of exposures.
- Repeating patterns are detected faster than novel patterns (implicit learning effect), and this can replicate remotely.
- Reward mechanics online introduce complexity/trust issues that may weaken or wash out the reward effect.

---

## 4) Why an A/B-style experiment
I chose an A/B-style experimental manipulation because the decision required **causal evidence**, not just preference:
- Reward level can be controlled and compared within participants
- Success metrics are measurable (reaction time + accuracy)
- The approach is compatible with remote delivery and fast iteration on task UX

---

## 5) Study design 
Participants completed a remote detection task where repeating patterns appeared over time; they responded as soon as they detected a transition. 
I manipulated incentive level (high vs low reward) for a subset of repeating patterns and compared detection performance using reaction time and accuracy.

---

## 6) Remote implementation and data quality
**Remote stack:** online experiment platform + online participant recruitment  
**Key design choices to manage remote noise**:
- **Headphone screening** to reduce audio variability
- **Baseline reaction-time calibration** using a simple control task
- **Clear exclusion criteria** for low engagement/low accuracy
- Focus on **relative performance** (e.g., repeating vs novel RT advantage) to reduce device-dependent variance

---

## 7) Metrics 
**Primary outcomes**
- **Reaction time (RT)** to pattern transitions  
- **Sensitivity / accuracy** in detecting transitions (including robustness checks)

**Guardrails / quality**
- Engagement thresholds (minimum accuracy, response patterns)
- Baseline control RT to contextualize individual differences

---

## 8) What we learned
### What replicated well online (feasibility)
The core implicit learning signal replicated: **repeating patterns were detected faster than novel patterns**, suggesting the paradigm can work remotely when designed carefully (screening + baselines + robust metrics).

### What did *not* replicate (reward effect)
The **additional benefit of high vs low reward** did not reproduce reliably in the initial online implementation.

Rather than treating this as “no effect,” I framed it as a **research-experience insight**: the reward mechanics themselves introduced UX and motivational risks that can blunt the intended manipulation.

---

## 9) Interpretation 
From a UX/process standpoint, the online reward version introduced extra complexity and potential confounds:
- **Cognitive load:** reward + attention checks + speed thresholds increased task demands
- **Trust/motivation:** reward may feel less “real” online without immediate proof of payout
- **Inconsistent reinforcement:** performance-gated rewards can weaken the association if “high reward” isn’t consistently received

---

## 10) Actionable next steps
If the goal is to test incentive effects remotely with higher confidence, I would iterate the experience in three ways:

1. **Reduce cognitive load**
   - Simplify feedback (fewer states, clearer language)
   - Remove or soften attention checks that feel like “gotchas”

2. **Increase trust and perceived fairness**
   - Provide a small guaranteed bonus during practice to demonstrate payouts
   - Make reward rules visually simple and predictable

3. **Make reinforcement consistent**
   - Avoid reward logic that depends heavily on tight RT thresholds
   - Separate “correctness feedback” from “reward feedback” to reduce confusion

**Follow-up study design:**  
Run a smaller pilot comparing the *simplified reward UX* vs the original reward UX, using the same quality gates, before re-testing the high vs low reward hypothesis.

---

## 11) How this reflects my research process
- Start with a decision and constraints, not methods
- Choose the lightest method that can answer the question causally
- Design for remote data quality (screening, baselines, guardrails)
- Synthesise into trade-offs + clear next steps
- Treat the study experience as part of the system: if UX changes outcomes, iterate it


