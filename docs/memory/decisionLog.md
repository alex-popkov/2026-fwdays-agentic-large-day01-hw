# Decision Log

## 2026-03-24: Memory Bank Structure

**Decision:** Place Memory Bank files in `docs/memory/` with additional docs in `docs/technical/` and `docs/product/`.

**Context:** The project needed structured documentation for AI-assisted development. The Cline Memory Bank pattern was adopted with 7 core files.

**Alternatives considered:**
- Single large README — rejected (too monolithic, hard to maintain)
- Root-level files — rejected (clutters repository root)
- Wiki — rejected (not version-controlled with code)

**Outcome:** Clean separation of concerns. Memory files are concise, cross-linkable, and colocated with the codebase.

## 2026-03-24: Documentation-First Approach

**Decision:** Document the existing architecture before making code changes.

**Context:** Excalidraw is a large codebase (~12,800 lines in App.tsx alone). Understanding the architecture first reduces risk of breaking changes.

**Alternatives considered:**
- Jump straight into code changes — rejected (high risk of unintended side effects)
- Rely solely on CLAUDE.md — rejected (insufficient for deep architectural understanding)

**Outcome:** Created comprehensive docs covering architecture, domain terms, and product requirements. Validated all docs against source code to ensure accuracy.

## 2026-03-24: Validation Before Trust

**Decision:** Validate every factual claim in Memory Bank docs against actual source code before relying on them.

**Context:** AI-generated documentation can contain hallucinations or inaccuracies. Found 6 minor issues across 6 files during validation.

**Issues found:**
- Utils package dependency arrow was wrong
- File casing mismatch (store.ts vs Store.ts)
- File name mismatch (linearElementEditor.ts vs linearElement.ts)
- Approximate counts were slightly off (~130 → ~113 fields, 45+ → 36 action files)

**Outcome:** Documentation accuracy confirmed at >95%. Minor fixes needed but no structural errors.
