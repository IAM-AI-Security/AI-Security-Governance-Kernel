# AI Security Governance Kernel

An authorization architecture for AI agents operating in cloud
environments, built so that an agent can propose an action and cannot
execute one.

**[Watch the walkthrough](https://youtu.be/M61Aq7VrniQ)**, four and a half
minutes, running against live AWS and Azure, including four attempts to
get around the controls.

## The problem

An AI agent given work in a cloud environment needs permissions to do it.
An agent that can fix a permissions problem can also change permissions,
grant access, revoke it, and disable the logging that would show it
happened.

The usual control is instructions telling the agent what not to do. The
agent is then the thing deciding whether to follow them.

This is built the other way.

## The principle

AI reasons. Deterministic policy authorizes. A separate component
executes. Independent verification confirms the result. Signed evidence
records it.

No agent action is authorized by a credential the agent holds.

## What the system implements

Each row below is shown running in the walkthrough linked above.

| Capability | Status |
|---|---|
| Policy evaluation as a decision point, default deny | Implemented |
| Human approval bound to one action on one resource | Implemented |
| Approval signing with an asymmetric key the agent cannot use | Implemented |
| Approval expiry and single use | Implemented |
| Scoped short-lived credential issuance | Implemented |
| Execution by a component separate from the agent | Implemented |
| Independent verification on a separate credential path | Implemented |
| Evidence chain with object-level retention | Implemented |
| Production operations, on-call, SLOs | Not claimed |

## Demonstrated

The walkthrough shows one governed transaction end to end against live
AWS and Microsoft Azure, and four attempts to bypass the controls. Each
was refused, each left the target unchanged, and each wrote a record.

---

**Security Architect @ Go Cloud Architects**

Contact: curtis@igasecurityconsulting.com
