# Code of Conduct — `risk-management` module contribution

> Composed into each deployment's `CODE-OF-CONDUCT.md` (`MODULE-SPECIFICATION.md`
> §6.2): the `## 3.` section below is inserted at the end of the deployed §3,
> and the `## 4.` section at the end of the deployed §4, each under a
> `### From module risk-management` heading.

## 3. Standard document types

| Type | Folder | ID prefix | Grounded in |
|---|---|---|---|
| Risk | `risks/` | `RISK-` | the rules it threatens (`Threatens`) |
| Control | `controls/` | `CONTROL-` | the rules it carries out (`Implements`) |
| Incident | `incidents/` | `INCIDENT-` | the rules it broke (`Breaks`) |

What each needs and when it closes: `Rules-of-Rules.md`, the module's part
(RISK-L1, `rr-RISK-001` to `rr-RISK-003`).

## 4. Slash-command entry points

- `/create risk <title>` (`/create-risk`) — record a risk immediately against
  the rules it threatens, with its likelihood, impact and owner, registered in
  `risks/risks.md`.
- `/create control <title>` (`/create-control`) — record a control carrying
  out rules and treating risks, registered in `controls/controls.md`; each
  risk it treats cites it back.
- `/create incident <title>` (`/create-incident`) — record an incident
  against the rules it broke and the risks that materialised, registered in
  `incidents/incidents.md`.
- `/risk-register` — summarize the open risks by likelihood and impact, with
  their controls and the controls' states.

When the user enters `/create risk: ...` or `/create-risk: ...`, run `catalyst new RISK --title "<t>"
--field Threatens=<rule IDs> --field Domain=<CODE> --field Likelihood=<value> --field Impact=<value>
[--field Owner=<name>] --command /create-risk --tier risk --as <signer>`, then write its
Description and Assessment from what the user said. If the rule it threatens,
the likelihood or the impact cannot be inferred, ask for them first; never
guess an impact.

When the user enters `/create control: ...` or `/create-control: ...`, run `catalyst new CONTROL
--title "<t>" --field Implements=<rule IDs> --field Kind=<Preventive|Detective|Corrective>
[--field Treats=<RISK-ids>] [--field Owner=<name>] --command /create-control --tier risk --as <signer>`
(it cites the control back in each treated risk's `Controls`), then write its
Description. Set it `Effective` only with its Evidence written (`rr-RISK-002`).

When the user enters `/create incident: ...` or `/create-incident: ...`, run `catalyst new INCIDENT
--title "<t>" --field Breaks=<rule IDs> --field Severity=<Low|Medium|High|Critical>
[--field Risks=<RISK-ids>] [--field Occurred=<YYYY-MM-DD>] --command /create-incident --tier incident
--as <signer>`, then write What happened. It closes only with its Lessons
(`rr-RISK-003`).

When the user enters `/risk-register`, read `catalyst list RISK --json` and
`catalyst list CONTROL --json`, and report the open risks grouped by impact,
then likelihood, each with its owner and its controls and their states; name
any risk treated only by `Planned` or `Ineffective` controls. Change nothing.
