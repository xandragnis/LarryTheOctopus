# Project: Larry The Octopus
**Core Intent:** A self-contained browser game (guide Larry to catch donuts) that runs on anything with a browser — mobile or desktop.

## Feature: Offline standalone build
**Intent:** Produce a version that runs with zero network access (works offline on mobile/desktop), while keeping the CDN-based file as the editable source.
**Constraints:**
- Leave `LarryTheOctopusUpdated_Enhanced.html` untouched as the editable source.
- Output a new file: `LarryTheOctopus_standalone.html`.
- Music (`LarysWater.mp3`, 7.8 MB) stays a **sibling file**, referenced relatively (per user decision).
- **Compile the build tools out:** precompile JSX → plain JS (drop the ~3 MB Babel), Tailwind → static CSS.
- Inline React 18.3.1 + ReactDOM 18.3.1 + Tone 14.8.49 (UMD) + generated Tailwind CSS.
**Edge Cases:**
- `</script>` sequences inside inlined JS must be escaped (`<\/script>`).
- All 22 classNames are static literals (0 dynamic) → full static Tailwind extraction is reliable.
- Relative music URL must resolve as a sibling on both `file://` and `http://`.
- Keep the existing custom `<style>` (overscroll/overflow) and all mobile meta tags.
**Acceptance:** (all met — verified in-browser 2026-06-17)
- [x] Standalone loads with 0 console errors (only a cosmetic favicon 404).
- [x] Zero network requests to external hosts (only local HTML + internal blob + sibling mp3).
- [x] Start menu renders; START GAME begins gameplay (live 488x648 canvas).
- [x] Styling matches the original (Tailwind gradient / computed styles verified).
- [x] Music loads from the sibling `LarysWater.mp3`.
- [x] Original source file unchanged (assembler only reads it; emits a new file).
**Files:** `LarryTheOctopusUpdated_Enhanced.html` (source, read-only), `LarryTheOctopus_standalone.html` (new), `LarysWater.mp3` (sibling).
