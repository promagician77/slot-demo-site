# Nocturne Reef demo site (prebuilt)

Static build of the slot demo. Nothing to install or build.

    npx vercel deploy --prod

`vercel.json` serves `site/`, sends `X-Robots-Tag: noindex, nofollow` on every response, caches hashed assets for a year, and leaves framing allowed so operators can embed the game in an iframe.

Pages: `/` (the game), `/notes.html` (build notes with the measured results).

## Measured vs not measured

Measured on this build (details on /notes.html):

- Return to player: 96.38% (±0.08%)
- Full-game check: 96.00% (±0.42%)
- Real session code path: 96.77% (±3.06%)
- Hit rate · volatility: 42.0% · SD 6.79× bet
- Random numbers: p = 0.132–0.996
- Engine tests: 38/38 pass
- No outcome logic in renderer: Pass
- Balance reconciliation: 100 rounds, 0 mismatches
- Resume after reload: Pass
- Lost reply: Pass
- Replay (game recall): Pass
- UK rule profile: 2,516 ms min cycle
- Layouts: 5 viewports, 0 issues
- Accessibility: 0 issues in 14 scans
- Sound: 12 cues, peak 0.365
- Memory: 6.22 → 9.33 MB
- Scene update cost: 0.10 ms median
- Load: 294 KB

Not measured:

- Frame rate on real phones and GPUs. The test machine renders WebGL in software, so frame rates there say nothing about devices.
- Real iOS Safari and Android Chrome hardware: audio unlock, notches and safe areas were checked only in emulated viewports.
- Lab certification (GLI, BMM, iTech). The chi-square and RTP runs are engineering checks, not a certificate.
- Your art direction. The symbols are my own placeholder illustrations, drawn in code.
- Spine animation. The demo has none; your Spine files would plug into the same symbol and win hooks.
- A real wallet or aggregator. The Node server keeps sessions in memory.
- How players respond to the math (feel, session length, feature pacing).
