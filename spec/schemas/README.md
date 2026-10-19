# SSoR schemas — v0.1 draft

**Status:** draft material for roadmap item 1–2 review. Not yet the specification's
published schemas; JSON Schema 2020-12.

| File | Record type | README section |
| --- | --- | --- |
| [`defs.json`](defs.json) | Shared definitions — origins, bitemporal times, supersession, provenance, audiences, CloudEvents keys | Key terms, §Design |
| [`episode.json`](episode.json) | **Episode** — something that happened, as received | What SSoR records |
| [`assertion.json`](assertion.json) | **Assertion** — typed claim + valid/record time + origin | What SSoR records |
| [`derivation.json`](derivation.json) | **Derivation** — lineage (W3C PROV-O terms) | What SSoR records |
| [`trace.json`](trace.json) | **Trace** — a decision + exactly what the decision-maker was shown | What SSoR records, §4 Reproducible decisions |
| [`decision-context.json`](decision-context.json) | *Supporting* — groups reads for one decision | What SSoR records |
| [`read-receipt.json`](read-receipt.json) | *Supporting* — exactly what one read delivered | §4 Reproducible decisions |
| [`refs.json`](refs.json) | Cross-system reference grammar (`dsor:`, `ksor:`, `trace:`) | §5.1 of the boundary spec |

## Conventions

- **Server-assigned fields are `readOnly` or absent from payloads**: `origin`, `recordTime`,
  `receiptsAttached`, `receipts`, `outcome`. Origins are assigned at admission from
  identity + authority map, never taken from the payload (boundary rules B-07, B-15).
- **Nothing is edited in place.** Corrections set `supersedes`; the superseded record
  stays and gains `supersededBy`. Resolutions supersede nothing (B-18, B-19).
- **All `$id`s are placeholders** (`ssor.example.com`) until the spec pins a canonical
  home; relative `$ref`s between files are authoritative for now.

## Open points (tracked in issues #1–#7)

- Matter linkage on episodes is a supersedeable claim, not a payload field — exact shape
  pending issue #1.
- `authority` entries assume the authority-map record shape from issue #4.
- Provenance minimum (inputs closure) pending issue #3.
- `policy.controlVersions` pairing pending issue #7.
