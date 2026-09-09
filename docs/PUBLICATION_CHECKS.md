# Publication checks

*Local validation recorded 9 September 2026 for the first public teaching
edition.*

These checks cover the textbook build, the publication inventory, the focused
reproduction tests, the fluid simulator self-tests, browser rendering under the
project base path and a secret scan. They do not certify any mathematical
result. The public repository's CI reruns the build, inventory and simulator
checks on the hosted runner.

## Environment

| Item | Value |
| --- | --- |
| Local system | macOS 26.1, Darwin arm64 |
| Build interpreter | CPython 3.11.14, isolated virtual environment |
| Markdown | 3.8.2 |
| Local pytest | 9.1.1 (CI pins 8.3.3) |
| Node.js | v25.8.0 (local) |
| Browser | Installed Google Chrome driven by Playwright |
| Gitleaks | 8.30.0 |

## Results

### 1. Textbook build, links, anchors, claim dependencies and source hashes

Command: `python scripts/build_textbook.py`

Result: exit 0 — `Built 28 pages; validated all HTML local links and claim
dependencies; copied 220 source files.`

The build verifies that the readable claim register matches
`textbook/claims.json` and rejects a stale register;
`python scripts/build_textbook.py --update-claim-index` regenerates the
register. The build also verifies every pinned `source_sha256`, validates HTML
local links and anchors, and copies the linked sources into the site.

### 2. Claim source hashes

Result: 117 of 117 pinned sources are present with matching SHA-256. One pinned
source hash was refreshed after editorial review: `docs/STATUS.md`, which was
rewritten for this edition. The other 116 pinned sources were not edited.

### 3. Focused reproduction tests

Command: `PYTHONPATH=. python -m pytest -q tests/ --ignore=tests/test_publication_inventory.py`

Result: 102 passed.

Command: `python -m pytest -q tests/test_publication_inventory.py`

Result: 6 passed, after `docs/PUBLICATION_INVENTORY.json` was generated.

### 4. Fluid simulator self-tests

Command: `node textbook/assets/fluid/checks.js`

Result: exit 0 — 16841 numerical assertions (DFT/FFT, projection and
dealiasing, ABC decay at both grids, nonlinear refinement), periodic sampling
and worker reset/step/tracer smoke checks, and worker request/error protocol
checks.

### 5. Browser rendering under the project base path

The built site was served at `http://127.0.0.1:8766/transformatics/` and nine
pages were loaded in two true viewports with installed Chrome through
Playwright: desktop 1440×900 and phone 390×844 with mobile, touch and device
scale factor 3.

Result: 18 of 18 responses returned 200. No console errors, page errors, failed
requests or horizontal overflow were recorded. The simulator worker started and
ran without errors.

Receipts: `/tmp/tfpub_receipts/browser_report.json` and the
`desktop_*.png` and `phone_*.png` screenshots in the same directory. These are
local receipts and are not committed. The temporary server was stopped after
the run.

### 6. Secret scan

Command: `gitleaks dir <staged snapshot> --redact --report-format json
--report-path /tmp/tfpub_receipts/gitleaks_public.json`

Result: 0 findings across 245 staged files and 2 symlinks (about 3.1 MB
including the inventory file itself). The report is redacted and contains no raw
credential material. No credential value is recorded in this document.

### 7. Hygiene and included third-party material

- The staged snapshot contains no `.git` directory, virtual environment,
  `_site` output, `.DS_Store`, `__pycache__`, `node_modules` or pytest cache.
- The largest included file is `textbook/claims.json` at about 81 KB; the
  inventory records 244 files, 2 symlinks and about 3.0 MB of file content
  (3.4 MB on disk including filesystem blocks).
- Two relative symlinks are included: `AGENTS.md` and `CLAUDE.md` point to
  `design.md` inside the repository.
- One preserved verification receipt,
  `formalization/oblique_cone/receipt.json`, records local build paths under
  the local volume label. It contains no personal name. The receipt is a claim
  source and was retained byte-identical; it was not edited to remove path
  cosmetics.
- No third-party source is vendored. MathJax 3.2.2 is loaded from a pinned
  jsDelivr CDN under its own license, and the site footer records it. The
  external OpenAI Lean sources are referenced by URL and commit and are not
  redistributed. The fluid laboratory has no npm dependencies. This is a review
  of the included material, not an exhaustive legal clearance.
- The root [MIT license](../LICENSE) is included and is copied into the built
  site as `LICENSE.txt`.

## Scope

These results describe the local snapshot. GitHub Actions reruns the build,
inventory and simulator checks on the public repository; the browser and secret
scans are local receipts, not CI jobs. None of these checks certifies a
mathematical proof, the external forced construction or the completeness of the
research record.
