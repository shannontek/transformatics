# Reading the dated research record

*Guide added 8 September 2026; updated for the public teaching edition.*

This repository includes a dated research record: experiments, failed routes,
corrections and proof notes produced while the questions were being worked out.
The record is evidence of the process, not a current statement of what is
established. This guide explains how to read it without mistaking an old label
for present standing.

## Where current standing lives

- [STATUS.md](STATUS.md) — the canonical short statement of what is open,
  retired, imported, written or formally checked.
- [textbook/claims.md](../textbook/claims.md) and its
  [machine-readable source](../textbook/claims.json) — the readable claim
  register, with a plain-language evidence record for each claim.
- [PUBLICATION.md](../PUBLICATION.md) — the release setup, included scope and
  recorded checks.
- [formalization/](../formalization/) — exact formalization scopes, builds and
  receipts.

If a dated document disagrees with these files, the current files govern. A
later dated correction supersedes an earlier positive label; the correction is
kept next to the claim it retires, not deleted.

The complete dated archive, including the full research graph, earlier status
snapshots, early planning documents and the pre-publication operational log, is
preserved in the private
[research archive](https://github.com/Hmbown/transformatics-research-archive).
This public snapshot includes the research notes cited by the book.

## How the record is organized

- `docs/` top level: research notes, strategy documents and audit records,
  usually named with a date (`..._2026_09_08.md`).
- `docs/ANALYSIS_NOTES/`: focused calculations and probes.
- `formalization/`: Lean sources, build receipts and scope statements.
- `artifacts/`: run outputs and receipts cited by the claim register. These are
  historical evidence, not current summaries.
- `experiments/` and `tests/`: the programs and checks associated with those
  records.

## How to read a dated claim

1. Read the date in the filename or at the top of the document.
2. Find the same question in [STATUS.md](STATUS.md) or the claim register. The
   current entry says what survives.
3. Keep the evidence axes separate: provenance (who produced the result),
   proof status (what was written), review (who checked it, if recorded) and
   formalization (what a machine actually checked).
4. Treat words such as `PROVED`, `VERIFIED`, `CERTIFIED` and `RIGOROUS` in old
   documents as the vocabulary of their date. They do not by themselves mean a
   current kernel check, an external expert review or a published theorem.
5. When reconciling an earlier positive claim, prefer documents whose titles
   include `AUDIT`, `CORRECTION`, `SUPERSEDED` or `RETIRED`.
6. Where an old document says a model review was "independent", read that as a
   separate model instance reviewing the work, not as external human expert
   acceptance. The claim register states the reviewer type when the record
   identifies it.

## Representative documents that need context

- [TRANSFORMATICS_DISCIPLINE.md](TRANSFORMATICS_DISCIPLINE.md) — historical
  method document; its status vocabulary predates the current register.
- [NSE_QGSO_CAP_VACUITY_2026_09_06.md](NSE_QGSO_CAP_VACUITY_2026_09_06.md) —
  the correction that retired the averaged-noncollapse route; read it before
  any earlier document that proposes that route.
- [PROOF_CHAIN_AUDIT_2026_06_09.md](PROOF_CHAIN_AUDIT_2026_06_09.md) — an
  audit of an earlier proof chain, retained with its corrections.

## Scope of this guide

This guide describes the included research record and the current summary
documents that govern it. It is not an end-to-end review of the record. It
re-verifies no mathematical result and alters no historical receipt. Source
hashes in the claim register are refreshed only after the corresponding source
text has been reviewed.
