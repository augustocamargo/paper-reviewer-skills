---
name: paper-citation-check
description: >
  Verify a paper's references/citations: each entry is a real work with correct
  author, title, venue, year, and DOI (not a placeholder or fabrication); the
  bibliography resolves with no undefined citations; and there are no
  defined-but-uncited or cited-but-undefined entries. Use when the user says
  "check the references", "are the citations real", "verify the bibliography",
  or "find placeholder/fake citations".
---

# Citation / reference reality-check

## Procedure
1. **Cited vs defined.** Diff the keys cited in the text against those defined
   in the .bib: list cited-but-undefined (will break) and defined-but-uncited
   (dead entries).
2. **Reality check each entry.** Flag stubs/placeholders (e.g., "and others",
   wrong/guessed venue, missing pages, suspicious author names). For doubtful
   ones, **web-verify against an authoritative source** (DOI, ACL Anthology,
   publisher page, or your venue's digital library) and correct the metadata — keep the citation
   **key** unchanged so no `\cite` breaks.
   - A *real* entry can still carry the **wrong paper's author list or DOI**
     (e.g., a Whisper entry holding CLIP's authors; a DOI that resolves to an
     unrelated work). Don't stop at "the work exists" — **verify the author list
     and actually resolve every DOI** to confirm it lands on the cited paper.
3. **Prune orphans.** Remove defined-but-uncited entries from the .bib (dead
   weight a reviewer may read as padding) once confirmed unused.
4. **Post-cutoff / unverifiable** entries (newer than your knowledge): flag as
   "could not verify" rather than asserting; ask the author to confirm.
5. **Clean compile.** After fixes, run `pdflatex → bibtex → pdflatex ×2` and
   require **0 undefined citations/references**.

## Reference-checker tools: errors vs warnings
If using an automated ref-checker, read its two signal classes differently:
- **Errors** (wrong author list, DOI resolving to an unrelated paper) are
  **gold** — hard to catch by hand. Act on them.
- **Warnings** about year/venue are usually the tool comparing **your correct
  published-venue metadata** against an arXiv/preprint label for the same work.
  These are typically **not** bugs — don't "fix" your correct entry to match a
  preprint. Verify before changing.

## Principle
Verify before changing. A real-looking arXiv ID or a plausible venue is not
proof; check the source. Don't "correct" an entry to a value you haven't
confirmed — that can replace one error with another.

## Output
- Table: `key | issue (placeholder / wrong venue / wrong author / OK) | verified source | fix`.
- List of uncited and undefined keys.
- Confirmation the bibliography resolves clean.
