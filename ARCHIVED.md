# ARCHIVED

This fork was an experiment in privileged-surface integration with local-brain
(2026-04 → 2026-05). It is now archived.

This file lives in the **external** `tolaria-local-brain/tolaria` repository.
It is unrelated to the in-repo `local-brain/app/` Tauri shell (which has its
own lifecycle governed by `local-brain/docs/specs/CLOSEOUT_PLAN-second-brain-v2.md`).

## Why

After comparative analysis of 15 second-brain peers
(`second-brain/docs/research/second-brain-comparative-analysis.md`), the
engine/surface boundary held but the **choice of the external Tolaria fork as
the privileged surface did not**. Every reviewed project that picked an existing
markdown editor (Obsidian) avoided the fork tax we hit (50 files, 2.8k LoC,
upstream 157 commits ahead, predicted conflicts in App.tsx / Editor.tsx,
≤10-touchpoint budget already over).

The decision and replacement plan are recorded in:

- `second-brain/docs/plans/IMPLEMENTATION-PLAN.md` (master plan)
- `second-brain/docs/plans/epics/EPIC-07-boundary-amendment-tolaria-sunset.md` (this sunset)
- `<spaces memory>/project_localbrain_tolaria_boundary.md` (boundary amendment)

## Replacement surfaces

- Skill pack — `.skill` packages for Claude Code / Cowork / Codex / Gemini CLI
  (local-brain `EPIC-02..EPIC-04`).
- Channel adapters — Email / Slack / WhatsApp (`EPIC-06`).
- Obsidian companion plugin (`EPIC-11`, P1).
- `sb-desktop` (Electron) for tray / notifications (replaces in-repo `local-brain/app/`).
- Wails app for non-markdown views (`EPIC-19`, P4+).

## Status

- The fork is read-only as of 2026-05-10.
- Upstream Tolaria is unmodified by this fork's archival.
- No future PRs into local-brain depend on this repo.
- The repo is preserved as an audit trail; the GitHub-side "Archived" flag
  has been set so it is read-only and surfaces a banner.

## What stays valid here

The HTTP-client glue and the vault-watch wiring code in this fork are
exemplars of how a desktop surface can talk to local-brain. If we ever
build a custom desktop surface (post-EPIC-19), portions may be revisited
as reference material — they would not be merged.
