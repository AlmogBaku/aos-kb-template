# aos-kb-template

The default template tree `kb init` clones when scaffolding a new base (aos kit,
`capabilities/kb`). Mirrors `capabilities/kb/skills/init/templates/` in the kit's own
checkout — this repo exists only to give `kb init` a second, more discoverable
materialization path than a path buried inside the aos checkout.

`kb init` clones this repo (read-only, unauthenticated, no fork), drops its `.git`
history, substitutes `{{name}}`/`{{purpose}}`/`{{audience}}`/`{{sync_mode}}`/
`{{curation}}`/`{{curator}}` into every file, and proceeds exactly as it would with
`--templates <local-dir>`. Override the source with `kb init --template <url>`, or skip
the network step entirely with `kb init --templates <local-dir>`.

Two files are renamed on the way in, so that a name this repo needs for itself can never
collide with a name the rendered base needs:

| here | rendered to |
|---|---|
| `base.README.md` | `README.md` — the base's front door, for the human who opens it |
| `gitattributes` | `.gitattributes` |

This file (`README.md`) describes the template repo and is **not** rendered into a base.

Not meant to be cloned or read on its own — it has no meaning outside `kb init`'s
substitution step.
