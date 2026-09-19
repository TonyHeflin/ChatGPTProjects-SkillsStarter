# Deepening Patterns

Use this file only after the core review has already discovered a relevant branch. These are depth prompts, not a substitute for broad discovery.

## Authority, governance, and veto points

When outside approval or authority matters, deepen by asking:

- Who has formal authority, practical veto power, contractual leverage, or operational control?
- Is approval required before prototype, deployment, operation, data use, or response action?
- Are authority boundaries clear during emergencies, failures, or disputes?
- Can different authorities impose conflicting requirements?
- Does the proposal depend on informal cooperation that has not been secured?

## Physical deployment and facilities

When the proposal enters a physical environment, deepen by asking:

- Who owns or controls the space?
- What installation, mounting, access, power, cabling, egress, accessibility, fire, electrical, rigging, or labor constraints could apply?
- What changes between setup, normal operation, crowded operation, maintenance, and teardown?
- Can the technically best placement or configuration actually be installed, serviced, and removed?
- What happens when the environment changes after commissioning?

## Human and organizational behavior

When people must operate, trust, respond to, or maintain the system, deepen by asking:

- What incentives encourage misuse, workarounds, over-trust, under-trust, gaming, or neglect?
- What does a false positive, false negative, ambiguous output, or degraded state cause people to do?
- Who owns decisions, cancellation, escalation, maintenance, and incident review?
- What knowledge, staffing, training, response time, and handoffs are assumed?
- Does the proposal create a new operational obligation without assigning an owner?

## Economics and lifecycle

When cost or scale matters, deepen by asking:

- What costs exist beyond component or acquisition price: installation, integration, validation, staffing, support, downtime, replacement, insurance, compliance, data, training, migration, and retirement?
- Which costs scale linearly, superlinearly, or in steps?
- What utilization or adoption assumptions carry the business case?
- What happens if success is slower, smaller, or more expensive than expected?
- What alternative use of the same money or staff could produce most of the benefit?

## Legal, privacy, policy, and insurance

When the proposal creates data, surveillance, safety, security, employment, financial, public-facing, or consequential actions, deepen by asking:

- Which exact behavior could create legal, contractual, privacy, evidentiary, regulatory, or policy exposure?
- What jurisdiction, venue, relationship, data type, retention practice, representation, or action determines applicability?
- Is the proposal assuming legality or insurability from silence?
- Could marketing or contractual claims create obligations beyond validated performance?
- Who bears liability and who is insured for the specific failure modes?

Do not assert a legal or insurance conclusion without appropriate evidence.

## Technology and integration

When a technology subsystem matters, deepen by asking:

- What happens at boundaries: clocks, schemas, APIs, protocols, identities, versions, retries, retries under load, stale state, partial failure, and degraded dependencies?
- What is measured end-to-end versus inferred from component health?
- Can a subsystem appear healthy while its actual function is broken?
- What assumptions are hidden by abstraction layers or vendor claims?
- What happens during update, rollback, migration, key rotation, credential loss, or dependency change?

## Security and abuse

When malicious or strategic behavior is plausible, deepen by asking:

- What is the cheapest way to create a harmful false positive, false negative, denial of service, or misleading state?
- What can an insider do that an outsider cannot?
- Which trusted inputs can be forged, replayed, suppressed, biased, or poisoned?
- Does the system create a new high-value target or new information useful to an attacker?
- Does a mitigation move risk elsewhere?

## Validation and evidence

When the proposal depends on testing, models, forecasts, experiments, or benchmarks, deepen by asking:

- Does the test environment reproduce the conditions that matter?
- What important mechanism is missing from the proxy or simulation?
- Are acceptance criteria defined before testing?
- Can the experiment distinguish competing failure causes?
- Are negative cases, rare events, degraded states, and adversarial cases represented?
- Can success in a proxy test be incorrectly promoted into a production claim?

## Transition, reversibility, and exit

When implementation changes existing systems or commitments, deepen by asking:

- What must be migrated, retrained, decommissioned, renegotiated, or operated in parallel?
- Can the organization return to the previous state if the change fails?
- What data, contracts, hardware, staff, or dependencies become stranded?
- What is the cost and time to unwind the decision?
- Does the proposal create lock-in before value is proven?
