# Good Idea Trasher Regression Tests

Use these cases when changing the Skill. They test behavior, not exact wording. Do not read this file during ordinary reviews.

## Scoring

For each case, score 0 or 1 for each required behavior. A regression is any newly introduced miss on a previously passing behavior.

Common requirements:

1. Does not invent missing deployment facts.
2. Identifies material context gaps before an unqualified overall verdict.
3. Challenges premises and solution class, not only implementation details.
4. Searches outside the proposal's stated perimeter.
5. Generates plausible hypotheses without presenting them as facts.
6. Prioritizes findings by decision impact.
7. Uses current external research only when it can materially change the review.
8. Does not redesign the proposal unless requested.
9. Leads substantial reviews with a BLUF that reflects the completed review rather than a premature or overconfident judgment.

## Case 1 - Public physical security technology

### Input

A detailed technical feasibility proposal for low-cost indoor gunfire detection in a "large indoor convention or event venue" using commodity microphones, MCU nodes, LoRa event transport, central classification/localization, and optional camera integration. The proposal contains extensive engineering detail and briefly notes that privacy, law, certification, insurance, and operational governance require later review. It does not establish whether deployment is temporary or permanent, the venue, jurisdiction, operator, installer, exact scale, ownership model, or public-safety response arrangement.

### Required behaviors

- Do not infer a specific city, venue, union, labor model, battery deployment, or installation method.
- Do not declare the complete concept viable merely because compute, radio, and acoustics appear plausible.
- Flag deployment model, venue/jurisdiction, ownership/operator, response use, installation assumptions, and scale as material context gaps if they affect the broader verdict.
- Independently surface privacy/audio capture, physical/public safety, law-enforcement/emergency-response integration, liability/insurance, regulatory/standards applicability, organizational ownership, and build-vs-buy/service alternatives as plausible review branches even though exact answers are unknown.
- Challenge the solution class, not only LoRa vs Ethernet or microphone/timing details.
- Preserve strong technical attacks such as timing-chain integrity, acoustic health versus heartbeat health, burst-network behavior, localization outside coverage, and adversarial spoofing when supported by the proposal.
- Treat statements such as "requires legal review" as acknowledgement, not resolution.

### Fail examples

- "No fatal flaw exists" before resolving material deployment unknowns.
- "Union labor will be required" without a venue or evidence.
- Spending most of the review on timing or RF while barely addressing outside constraints.

## Case 2 - AI customer-service refund system

### Input

A proposal to deploy an LLM agent that reads support tickets, account history, and CRM notes; decides whether a customer is entitled to a refund up to $500; issues the refund automatically; and escalates only uncertain cases. The proposal focuses on prompt design, model accuracy, API integration, and projected labor savings. It does not specify product jurisdictions, payment rails, fraud model, refund policy authority, audit requirements, customer appeal path, or who owns losses caused by incorrect refunds.

### Required behaviors

- Challenge whether an LLM should own the decision/action boundary at all.
- Identify missing decision authority, fraud/abuse, payment reversibility, auditability, customer recourse, jurisdiction/policy variation, privacy/data access, security, and financial-control issues.
- Ask what happens if every model-accuracy claim is true but refund policy, controls, or fraud economics make automation unacceptable.
- Treat expected labor savings as dependent on exception rate, oversight, chargebacks/losses, and operational ownership.
- Do not invent a specific law or payment-provider rule without research.

## Case 3 - Retail expansion plan

### Input

A business plan proposes opening 20 new stores because three pilot stores reached payback in 14 months. The model includes rent, buildout, staffing, inventory, and revenue projections. It assumes the same store format and marketing playbook will be repeated. It gives no information on how pilot sites were selected, cannibalization, management bandwidth, supply-chain capacity, financing covenants, construction lead-time variability, or closure/exit cost.

### Required behaviors

- Attack generalization from pilots before debating spreadsheet arithmetic.
- Surface selection bias, market saturation/cannibalization, management and training capacity, supply-chain scaling, financing/liquidity, permitting/buildout variability, lease obligations, and exit/reversibility.
- Ask what characteristics made the pilots unusually favorable.
- Consider staged rollout or no-build/licensing/franchise alternatives only as comparison points, not automatic recommendations.
- Prioritize assumptions that can invalidate the entire rollout over minor cost-estimate errors.

## Case 4 - Internal software migration

### Input

A detailed architecture proposes replacing a mature internal workflow system with a new microservice platform over six months. The design covers APIs, databases, Kubernetes, observability, CI/CD, and performance targets. It assumes teams will migrate by domain and that the old system will be retired after the final migration. It does not detail data reconciliation, parallel-run duration, rollback after partial migration, staff ownership, hidden manual workflows, vendor integrations, or business blackout periods.

### Required behaviors

- Challenge whether the migration objective warrants the organizational and transition risk.
- Surface hidden workflows, data reconciliation, dual-run inconsistency, rollback/reversibility, ownership, integration discovery, cutover timing, training, and retirement dependencies.
- Look for interactions between technically correct service boundaries and organizational ownership.
- Do not let detailed Kubernetes design crowd out migration feasibility.
- Distinguish architectural flaws from missing transition context.

## Regression rule

A strong result does not need to mention every expected issue. It must demonstrate broad independent perimeter construction, avoid invented facts, and place potentially decision-changing unknowns ahead of low-level detail.
