# SSOS pipeline walkthrough

A self-contained animated tour of how a farm-year submission moves through the Sans Souci
Carbon Footprinting Orchestration Platform — built for stakeholders and new starts.

**Everything depicted is synthetic / illustrative.** No real farm data, no live calls.

## Open it

`index.html` is the whole site — no build, no dependencies, no network requests.
Double-click it, or serve the folder with any static file server.

## Using it

- **▶ Play** / step with **›** / **‹** — **space** plays and pauses, **R** restarts.
- **Story** captions (default) are the plain-English version; **Engineer detail** swaps in
  the real stage names, containers, queues, artefact filenames and source files.
- Three scenarios: *A farm year's journey* (happy path), *Held for readiness* (a
  `blocker_owner: LMC` hold and resume), *Refused at the door* (a synchronous 422 that
  leaves staging evidence but starts no orchestration).

## Deep links

| Param | Effect |
|---|---|
| `?scenario=journey\|held\|refused` | pick a scenario |
| `&to=N` | jump straight to beat N |
| `&eng` | open in Engineer detail |
| `&play` | auto-play on load (handy for recording) |

e.g. `index.html?scenario=held&to=9&eng`.

## Recording

Play full-screen (`F11`) and capture the window — Windows Game Bar (`Win+Alt+R`) or OBS.
The timeline is deterministic, so recordings are repeatable.

## Provenance

Every stage, container, queue, artefact and lifecycle-state name is a real constant from
the platform's code. The embedded `#pipeline-manifest` JSON is checked against those
constants by `tests/test_pipeline_walkthrough_drift.py` in the
`carbon-footprinting-orchestration` repo — this file is a published copy of
`demo/pipeline_walkthrough.html` from that repo.
