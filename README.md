# Prism Plunge

Open index.html in a browser to play. No install, build, network, or external assets required.

- Drag horizontally or hold Left/Right (A/D) to rotate the tower. The unicorn bounces automatically.
- Flip reverses drag and keyboard controls and remembers your preference.
- R or Restart restarts the current level. Sound is optional; each cleared platform plays the next melody note.
- Level 1: 40 red platforms, with nearby gaps for longer drops.
- Level 2: 20 orange platforms, with larger gap offsets encouraging a bounce before each turn. Black tips beside both edges of every gap are lethal. Contact automatically restarts level 2, preserving completed red progress.
- Level 3: 20 yellow platforms mixing one, two, and three gaps. One- and two-gap floors have wider openings. Only alternating floors have a black tip (one tip each); some floors also have an interior black patch, and some are hazard-free. Dying restarts yellow and preserves red and orange progress.
- Levels opens a picker that pauses the game. Level 1 is always available; completing a level unlocks the next. Replay any unlocked stage independently. The three unbuilt stages remain unavailable.
- Completion and per-level best times are saved in this browser. Each attempt has its own timer, reset on restart or death; opening the picker pauses it. Faster completed attempts replace the saved best.
- Level 4: 20 green platforms with tall, striped blockers. When a wall reaches the unicorn, rotation stops; reverse direction to reach the gap around the other side. Walls alternate sides and respect the column depth.
- Every completed level shows its time and a Next Level button, plus Retry and Choose Level. Progression waits for your choice. After green, future stages remain unavailable.
- The seven-band rainbow HUD fills each colour after its level is completed. Red, orange, yellow, and green are playable.
- Platforms grow lighter toward the bottom. Broken fragments respect column depth; the fixed-screen unicorn casts a soft shadow and leaves more stars and sparkles during faster falls.

## Submission size

Only index.html is needed. game.zip contains that file, below both 13,000 and 13,312 bytes. Rebuild after edits with PowerShell:

    Compress-Archive -LiteralPath index.html -DestinationPath game.zip -Force
    Get-Item game.zip | Select-Object Name,Length

## Verification

Run node game.test.cjs for mocked-browser checks of level progression, rainbow completion, both black-tip collisions, level-only restart, safe bounces, all 20 bounce-and-turn orange floors, mixed yellow gap counts, sparse black tips, interior hazard patches and safe landing sections, four-level completion, Next Level transitions, blocker stops in both directions including large drags, all green alternate routes, saved unlocks and best times, picker pause/resume, and locked-level guards. Canvas drawing calls are exercised, but visual browser verification was unavailable because preview permission was declined.





