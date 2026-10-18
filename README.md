# catalyst-risk-management

A catalyst process module for risk management: **risks** (`RISK-`), the
**controls** that treat them (`CONTROL-`) and the **incidents** where they
materialised (`INCIDENT-`), each grounded in the rules it threatens, carries
out or broke.

- **`module.yaml`**: the module in catalyst's module format 3 — its tiers
  (`chore`, `risk`, `incident`), the namespace `RISK` of its meta-rules
  (`rr-RISK-NNN`) and invariants (`INV-RISK-n`), and its three types, from
  which catalyst generates each type's template and definition.
- **`rules-of-rules.module.md`**: its meta-rules, composed into the deployed
  `Rules-of-Rules.md`.
- **`code-of-conduct.module.md`**: its document types and commands
  (`/create risk|control|incident`, `/risk-register`), composed into the
  deployed `CODE-OF-CONDUCT.md`.
- **`INVARIANTS.module.md`**: the law it adds, RISK-L1.

Install it beside another module with `catalyst module install <this repository>`,
or as a deployment's first module with `catalyst init --module risk-management`.
It needs kernel 0.83.0 or later. It is catalyst's second module, the proof that
the kernel and the Studio name no module type (owner decision B1).
