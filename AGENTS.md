# AGENTS.md

## Unwritten
- Publishing: GitHub Pages serves `main` from the root, so a push to `main` is a release. There is no CI and no test suite.
- Gotchas: `index.html` and `DT_Task2_Voykovskiy_comparison_map.html` are byte-identical copies; change both or neither. The page fetches the three `.geojson` files by relative path, so open it through a local HTTP server, not `file://`. GeoJSON order is `[lng, lat]`.
- Conventions: page text is in Russian.
- Why: the conclusion is that the source file is genuine WGS84/CRS84 and needs no MSK-77 conversion for Yandex Maps; the MSK-77 round-trip layer exists only as proof, and the orange mismatch layer deliberately shows a ~21.7 m error from mixing MSK-77 implementations. Do not "fix" it.
- Off-limits: the three `DT_Task2_Voykovskiy_*.geojson` files are computed outputs with no generator script in this repo; do not hand-edit them.

## Pointers
- **Writing** or reviewing code: apply `CODING_STANDARDS.md`; project config and linters win where they disagree.
- **Security**-sensitive change (auth, permissions, untrusted input, secrets): read `docs/agents/security.md` first.
- **Committing** or opening a PR: follow `docs/agents/git.md`.
- **Risky** change (spans modules, migrates data, alters a public API): propose a phased plan and get approval before editing.
- **Done** means you ran the project's own check commands and they are green, or you named the ones you could not run.
