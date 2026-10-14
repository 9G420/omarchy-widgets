# Codex Quota and Resets

A Codex usage monitor with five-hour and weekly quota reset countdowns, usage history, a calendar, and public reset announcements. The widget includes English, Chinese, Japanese, Korean, Spanish, French, and German text.

## Update notes — 2.2.0

- Fixed the refresh control so tapping it requests a fresh quota scan.
- Added theme-matched tap feedback and a visible refreshing state for the quota controls.
- Reworked the compact and elongated layouts, including 2×2, 2×3, 3×2, 3×3, 3×4, 4×3, and 5×3, to keep content readable without clipping or overlap.

## Requirements

The widget uses Python 3 (`python` package). Quota data is read from the local Codex CLI state; no account data is uploaded by the widget.
