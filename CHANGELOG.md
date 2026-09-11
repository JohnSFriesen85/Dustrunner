# Dustrunner Crew Manifest — Changelog

The version shown in the corner of the app matches the entries here. This
file replaces the changelog that used to live as a comment inside
`index.html` — that comment is gone now; this is the one source of truth
going forward.

Everything before v1.0 is condensed, since it predates the app being
treated as a real versioned release.

## v0.1
Initial player-facing crew manifest tracker: tabs (All / per-character /
Sell), Log New Item form, plain-text Share Summary with copy-to-clipboard,
localStorage persistence.

## v0.2
Added Qty field to the log form. Items can be logged as stacks; displayed
value is unit value × quantity, name shows as "Item ×N" when N > 1.

## v0.3
Added Transfer: a button on every item row opens a modal to move an item
(or split part of a stack) to another character, the Sell pile, or a new
Unavailable status (lost / destroyed / given away). Added the Unavailable
tab.

## v0.4
Added "Download as .txt" for the Share Summary. Added Export Data / Import
Data (JSON) so the manifest could be handed off between players or devices
without losing session detail. (Removed again in v0.6 — see below.)

## v0.5
Replaced localStorage with a live Firebase Firestore backend. Everyone who
opens the page now sees the same data, updated in real time.

## v0.6
Removed Export Data / Import Data — no longer needed once the live backend
made manual handoff unnecessary. Share Summary stayed, since it solves a
different problem (a human-readable snapshot to paste outside the app).

## v0.7
Clear All now opens a themed in-app confirm modal instead of the browser's
plain popup. Share Summary reorganized to mirror the tabs (All, then each
character, then Sell, then Unavailable — Unavailable added to the summary
for the first time). Increased font sizes and widened the layout;
brightened muted colors for contrast.

## v0.8
Moved the item list below the Log New Item form so it reads as its own
section instead of looking like part of the form. Added a Settings modal
to add/remove characters — the roster is now shared and live instead of
hardcoded.

## v1.0
Marked as the first official release — same build as v0.8. This is the
point the app was considered stable enough to name and version going
forward.

## v1.1
- Added **Level** and **Weight/Bulk** fields to item logging, alongside
  the existing Name, Value, and Qty.
- Bulk accepts `L` (light — counted as 0.1 Bulk), `-` or `0` (no bulk), or
  a whole number. Anything else is kept as typed for display but excluded
  from bulk totals.
- Added a total Bulk figure (rounded down) next to the value total on the
  All tab and each character tab — covers that tab's kept items. Sell and
  Unavailable stay value-only, since those items aren't being carried.
- Added a version tag in the corner of the app.
- Moved version history out of the code entirely — this file is now the
  only changelog.
