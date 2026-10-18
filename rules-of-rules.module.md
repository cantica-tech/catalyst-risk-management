# Rules of Rules — risk-management module

> Module contribution (`MODULE-SPECIFICATION.md` §6.1): appended to the
> deployed `rules/Rules-of-Rules.md`, after the kernel's handbook, under
> `### From module risk-management`. It never replaces kernel content. Its
> meta-rules are numbered in the module's namespace, `rr-RISK-NNN`.

This module's work is risks (`RISK-`), the controls that treat them
(`CONTROL-`) and the incidents where they materialised (`INCIDENT-`), each
grounded in the rules it threatens, carries out or broke. Their fields,
statuses and files are the entity definitions' (`definitions/`).

## The tier decides the artifact (RISK-L1)

A chore changes no rule's behaviour and has no artifact. Assessing what
could break a rule is a risk; recording what did break one is an incident.
A control is opened when a risk is treated, never as a tier of its own.

## 1. `rr-RISK-001` A risk names what it threatens and is assessed before it is treated

A `RISK-` names the rules it could break (`Threatens`), its likelihood and
its impact, and who owns it. It is `Assessed` once the Assessment says why
those values hold, then either `Treated` by one or more controls, named
under its Treatment, or `Accepted` by its owner, the reason written there.
A risk is not closed while a control treating it is still `Planned`.

## 2. `rr-RISK-002` A control is effective only on evidence

A `CONTROL-` carries out rules (`Implements`) and treats risks (`Treats`).
It is `Implemented` when it is in place and `Effective` only once its
Evidence says how and when it was shown to work; a control found not to
work is `Ineffective`, and each risk it treats is assessed again.

## 3. `rr-RISK-003` An incident ends in lessons

An `INCIDENT-` names the rules it broke (`Breaks`), its severity and the
risks that materialised (`Risks`). It does not close until its Lessons say
what changes: a control added or strengthened, a rule changed, a risk
reassessed — each its own artifact or rule change, journaled.
