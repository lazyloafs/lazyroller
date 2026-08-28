LAZY ROLLER
Author: lazyloafs

INSTALLATION

1. Open your Ascension game folder.
2. Open Interface, then AddOns.
3. Extract the ZIP into the AddOns folder.
4. Verify that this file exists:

   Interface\AddOns\LazyRoller\LazyRoller.toc

   If you see LazyRoller\LazyRoller\LazyRoller.toc,
   move the inner folder up one level.
5. Fully restart Ascension. A first-time addon installation requires a full
   client restart; /reload is not enough to discover a newly added addon.
6. Enable Lazy Roller in the AddOns list if needed.
7. In game, type /lazyroller to open the window. You can also click the
   Lazy Roller button on the minimap.

LIVE ID CATALOG

- Install AscensionTalentExporter, then run /s10ids (or /s10catalog) in game.
  The command captures the live spell IDs and talent entry IDs into the saved
  exporter database. This release includes the latest captured Darkmoon export.
  Run /reload after exporting before continuing to play.

UPDATING

Extract the newest ZIP into Interface\AddOns and allow the existing
LazyRoller files to be replaced, then type /reload in game. Your settings
are stored separately by the game and are not removed when the addon folder
is replaced.

NOTES

- Lazy Roller is a standalone addon for Ascension's Season 10 Wildcard mode,
  paired with wildcardlogscopier.lazyloafs.workers.dev for build import. Paste
  the complete roster link, including its #build=v1 payload, into the addon.
  URL-encoded copies are accepted too. The comma-separated value from Copy IDs
  is also accepted and is converted into an editable build when you analyze it.
- Paste a complete build link or ID list into the planner and click Analyze
  (or press Enter). The Add boxes accept numeric IDs or fuzzy ability/talent
  names. Soul Link uses spell ID 19028; its legacy armory ID 40601 and talent
  ID 3342 are accepted and normalized to 19028. If an exact name has multiple
  live IDs, Add includes every distinct matching ID; rank IDs for the same live
  entry are analyzed as one target at the highest rank, while distinct entries
  remain separate. Partial names still use the best match. Clicking Add also
  loads the full build immediately, so
  additions are written directly into the editable
  planner instead of waiting as pending changes. Add can bootstrap an empty
  planner before the first analysis; later Analyze actions keep those entries.
  Right-click any unlocked listed entry to remove it, including entries from a
  standard analyzed build (which is converted to an editable build). Repeated legacy
  aliases for one canonical ID are normalized so an older saved link cannot make
  the planner appear empty.
- Support development: https://www.patreon.com/c/LazyLoafs504
- Every Single and Rapid session still requires explicit confirmation.
- Roll: Abilities and Roll: Talents both start checked. Clear either one to
  run only the other side. Changing the selection safely ends an active
  session, and the new selection needs another confirmed Start. With both
  cleared, Start is disabled. The minimized tracker marks a one-side session
  in amber.
- Minimize leaves a small draggable tracker and closes Character Advancement
  when it has no pending native draft. Escape does not close the tracker, so
  normal gameplay Escape presses do not pause rolling. During a session it
  shows Open, Pause/Resume, and Stop. Once idle, it shows only Open and Close.
  Each visible button group is right-aligned, and Open and Close match widths.
  Unexpectedly hiding an active tracker pauses the session. Combat does not
  pause while this tracker is active. Opening the full window during combat
  pauses rolling again.
- While minimized, result events update only the tracker and in-memory logs.
  The hidden workspace is rebuilt once when reopened instead of rescanning the
  character after every learned spell.
- Ability any-of groups keep the first learned choices in builder row order.
  When a higher choice is learned, the addon protects it first and rolls the
  displaced lower choice off before ordinary Ability cleanup. Only locks the
  addon previously verified, or effective any-of locks explicitly adopted by
  Sync desired locks, can be rotated across sessions; other locks stay manual.
- Rapid talent upgrades can trigger a one-shot Reload & resume recovery for a
  native client issue. Ascension requires an explicit click on the recovery
  button in either the minimized tracker or full workspace; the addon never
  attempts the secure UI reload from a timer. Recovery returns to the tracker
  when Reload was clicked there.
- Use /lazyroller trace to copy diagnostic state if a Rapid session gets stuck.
- Use /lazyroller gear (or /lazyroller export) to copy an Architect import link
  for the character's currently equipped gear. Open the copied link to use
  those exact item strings and observed item levels as a new gear-plan
  baseline.
- Builder v2 links carry ordered Manual and Auto synergy helpers. Auto helpers
  stay protected behind ordinary undesired entries only while one of their
  bracketed build targets is still missing or incomplete. Manual helpers
  remain last-resort entries until removed from the plan.
- Builder v3 links can mark any category Optional in addon. Use the switch at
  the end of its in-game category header, or the Auto-Roll categories overview,
  while no session is active. Disabled categories are absent from the rolling
  plan, and their targets cannot keep Auto synergies active.
- Active synergy rows are shown in the blue learned-outside-build list as
  [Target, Target 2] or [Manual]. Rapid clears ordinary discards on funded
  sides first, then projects one active synergy at a time in configured removal
  order and re-analyzes after each completed batch. An unfunded side cannot
  strand useful synergy work on the funded side.
- Every ordinary undesired entry receives a pity-pressure score from the
  reviewed synergy graph: talents count linked abilities and abilities count
  linked talents. Higher pressure is rolled off first within the same safe
  tier. Side scheduling counts pressure-bearing entries once each rather than
  summing their scores; the larger count wins and ties keep the scroll ratio.
  The plan rows and next-roll summary show the score, the A/T source counts,
  and the exact Single target or highest-pressure Rapid group.
