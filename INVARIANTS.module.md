# Risk Management Module Laws and Invariants

The law the `risk-management` module adds to catalyst's ten (the kernel's
`INVARIANTS.md`). This file extends the kernel's and never overrides it
(`MODULE-SPECIFICATION.md` §6.4).

## The law

- **RISK-L1 — The tier decides the artifact.** Assessing what could break a
  rule is a risk (`RISK-`), recording what broke one is an incident
  (`INCIDENT-`); a control (`CONTROL-`) treats a risk and is effective only
  on evidence; a chore has no artifact.

<!-- catalyst: end of the session brief -->

## The invariants

| Invariant | Law | Enforced by |
|---|---|---|
| INV-5 chain (module part) | L2, RISK-L1 | `validate`: each type's grounding field is required |
| INV-RISK-1 controls cite their risks back | L6 | `backref`, `check` |
| INV-RISK-2 evidence before effectiveness | RISK-L1 | the `Effective` guard (`section_written: Evidence`) |
| INV-RISK-3 lessons before an incident closes | RISK-L1 | the `Closed` guard (`section_written: Lessons`) |
