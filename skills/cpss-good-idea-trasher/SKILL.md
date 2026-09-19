---
name: cpss-good-idea-trasher
description: "Rigorously stress-test developed proposals, specifications, plans, architectures, policies, designs, and other reasonably specific ideas. Use when the user asks to review, evaluate, challenge, red-team, stress-test, pick apart, find flaws or omissions, ask \"what am I missing?\" or \"does this hold up?\", or otherwise wants a substantive adversarial assessment of a concrete proposal. Also use for proposal reviews where hidden assumptions, missing context, outside constraints, or failure modes matter. Do not trigger for casual brainstorming, simple preference questions, or undeveloped idea generation unless the user explicitly asks for adversarial review."
---

# Good Idea Trasher

## Objective

Stress-test the whole proposal, not merely the details it chooses to discuss. Find credible ways it can fail, disappoint, become uneconomic, create unintended consequences, or depend on unstated conditions. Attack the idea, not the user.

Do not try to prove the idea bad. Do not manufacture objections. Reward survivability under scrutiny.

## Core rules

- Treat the proposal's scope, framing, assumptions, and chosen solution as challengeable. A proposal cannot make a material issue irrelevant merely by labeling it out of scope.
- Distinguish user-provided facts, verified facts, embedded assumptions, hypotheses, inference, unresolved questions, tradeoffs, and recommendations. Do not present one as another.
- Use creative license to generate realistic attack hypotheses, branches, stakeholders, dependencies, and failure scenarios. Do not invent facts about the actual deployment or environment.
- Establish breadth before depth. Do not spend most of the review on an interesting implementation detail before checking for missing domains or context that could dominate feasibility.
- Treat silence as unknown, not evidence of irrelevance. A missing domain can itself be a major finding.
- Distinguish acknowledgement from resolution. "Needs legal review" or "insurance may apply" does not mean the issue has been adequately handled.
- Prioritize diagnosis. Mention a mitigation only when it materially clarifies severity or viability. Do not redesign the proposal unless asked.
- If the idea survives serious scrutiny, say so. Do not create criticism for balance.

## Review workflow

### 1. Reconstruct the proposal

Identify, from the material actually supplied:

- objective and claimed benefit;
- proposed solution and solution class;
- important constraints and success criteria;
- operating/deployment context that is actually established;
- consequential claims and decisions;
- assumptions that appear to be carrying the design.

Do not silently fill gaps with a convenient scenario.

### 2. Check reviewability and missing context

Before issuing an overall feasibility judgment, ask:

- What facts would materially change the attack surface, severity, or go/no-go decision?
- Which of those facts are established, and which are missing?
- Could the missing information conceal a fatal or program-blocking flaw?

When material context is missing:

- ask only the minimum clarification if the user needs a decision that cannot be defended without it;
- otherwise continue with conditional branches and label the judgment partial;
- flag unresolved material dependencies as findings.

Do not call a proposal viable, safe, production-ready, or free of fatal flaws when missing context could materially reverse that conclusion.

### 3. Attack the premise before the implementation

Challenge:

- whether the stated problem is the real problem;
- whether the desired outcome is defined well enough to judge success;
- whether important constraints are facts or inherited assumptions;
- whether the selected solution class is justified;
- whether a simpler, purchased, outsourced, manual, or no-build alternative could deliver most of the value with less risk;
- whether success itself creates new problems or obligations.

Ask: "If every internal technical claim were true, what could still make this a bad idea?"

### 4. Expand the real-world perimeter

Independently look for material things outside the proposal's own map. Derive them from the proposal; do not use a fixed checklist mechanically.

At minimum consider these discovery questions:

- Who can use, misuse, maintain, pay for, approve, block, regulate, insure, audit, depend on, be harmed by, or refuse the proposal?
- What organizations, authorities, vendors, facilities, infrastructure, contracts, policies, markets, or physical conditions does it depend on?
- What must remain true for the proposal to work?
- What happens during installation, transition, operation, degradation, failure, recovery, scaling, and retirement?
- What important chapter would a skeptical experienced outsider expect to see that is absent?
- What choices create downstream consequences in adjacent systems?

Generate plausible hypotheses for investigation. Mark them as hypotheses until supported.

### 5. Follow consequences across boundaries

For important choices, trace realistic chains such as:

`choice or assumption -> mechanism -> external consequence -> secondary constraint -> feasibility impact`

Look especially for interactions where individually reasonable decisions become dangerous, expensive, or incompatible when combined.

Stop tracing when additional links are unlikely to change severity or the decision.

### 6. Verify material external claims

Use current research when a material finding depends on facts that may vary by date, jurisdiction, venue, vendor, standard, market, law, policy, or product capability.

- Prefer primary or authoritative sources for consequential claims.
- Use secondary sources when independent interpretation or comparison helps.
- Surface material conflicts in evidence rather than silently choosing one.
- If verification is unavailable, keep the point as an unresolved hypothesis or conditional risk.
- Increase rigor for legal, financial, health, safety, security, privacy, compliance, or irreversible consequences.

Do not research merely to decorate the answer. Research when it can change a finding, severity, or conclusion.

### 7. Attack the implementation

After the perimeter is broad enough, go deep on the domains that matter. Examine normal operation and failure conditions. Relevant areas can include technical architecture, economics, human behavior, operations, security, privacy, law, policy, physical safety, maintenance, supply chain, organizational ownership, incentives, adoption, integration, testing, observability, recovery, scaling, and exit.

Do not force every review through every domain.

When an already-discovered branch needs deeper attack patterns, consult `references/deepening-patterns.md`. Do not use that reference as a substitute for the discovery steps above.

### 8. Prioritize and reassess

Rank findings by their ability to change the decision, considering consequence, plausibility, detectability, recoverability, uncertainty, and cost of being wrong.

Use severity when helpful:

- **Fatal** - defeats the central objective or requires fundamental change.
- **Major** - can materially impair success or independently block deployment/commitment.
- **Moderate** - meaningful weakness requiring mitigation or conscious acceptance.
- **Minor** - limited impact but worth noting.

For major findings, make the causal chain clear:

`condition or assumption -> failure mechanism -> consequence`

Then reassess the whole proposal. Do not let success in one subsystem stand in for feasibility of the complete system.

## Output behavior

Adapt the report to the proposal; do not force empty sections.

Lead substantial reviews with a **bottom line up front (BLUF)**: state the current verdict, the strongest reason, and any material limit on confidence. The BLUF is an output-order rule, not an analysis-order rule. Complete the breadth-first review before settling the verdict, then present that conclusion first. Do not imply stronger confidence than the review supports.

For substantial reviews, normally provide:

1. **BLUF / overall assessment** - current verdict, strongest reason, and whether missing context materially limits the judgment.
2. **Highest-impact findings** - fatal and major issues first.
3. **Missing context that could change the verdict** - when material.
4. **Hidden assumptions, dependencies, and outside-the-frame issues** - combine or separate as useful.
5. **Implementation weaknesses and failure scenarios** - proportional to importance.
6. **What survived attack** - only if useful to distinguish robust parts from unresolved ones.
7. **Decision boundary** - what must be learned, changed, or accepted before stronger confidence is justified.

For each major finding, distinguish whether it is a demonstrated defect, plausible risk, missing information, unsupported assumption, or unresolved external dependency.

Keep the review proportional. A short proposal does not require a giant report unless consequence or complexity warrants it.

## Interaction rules

- Do not praise-pad or create artificial balance.
- Do not use the user's confidence or sophistication as evidence that the proposal is sound.
- Do not let polished detail hypnotize the review. A 30-page proposal can still omit three facts that determine viability.
- Use known conversation, Project, and supplied-file context when available, but treat it as evidence subject to the same discipline unless the user explicitly establishes it as authoritative.
- Do not repeatedly ask for information already provided.
- If the user explicitly narrows scope, honor that scope and state when excluded domains could still affect any broader conclusion.

## Maintenance and evaluation

Use `references/regression-tests.md` only when evaluating, updating, or regression-testing this Skill. Do not load it during ordinary proposal reviews.


---
To read any file's contents, use `functions.exec` to run `text(await tools.skills__read({"uri": "skills://good-idea-trasher/<relative_file_path>"}))`.
Read once per file. Available relative file paths:

SKILL.md
agents/openai.yaml
assets/icon.svg
references/deepening-patterns.md
references/regression-tests.md
