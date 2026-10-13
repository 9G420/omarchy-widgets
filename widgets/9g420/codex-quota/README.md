# Codex Quota and Tibo Reset Monitor

A bilingual English/Simplified Chinese OWL 6 home-screen widget for local Codex quota snapshots and public reset announcements.

## Features

- Reads five-hour and weekly quota snapshots from local Codex session records. Quota values and the local cache stay on the device.
- Shows estimated reset countdowns, awaiting-confirmation states, recent quota-window changes, and reset-time notifications.
- Reads public Tibo announcements from the documented Codex Reset JSON API. It uses only `GET /api/feed` and `GET /api/timeline`, with a project-identifying User-Agent.
- Refreshes the public data every five minutes, observes the API's one-request-per-minute ceiling and `Retry-After`, and keeps the last valid cache when a request fails.
- Separates announced resets from credit announcements. Only a timeline event with `group: reset` and `announcement_state: announced` counts as a confirmed reset.
- Includes a calendar, selected-day records, monthly and 90-day counts, median confirmed-reset interval, source links, and a persistent language switch.

The widget displays a clickable **Data: codex-reset.com** credit next to the public data. The monitor is an unofficial community widget and is not affiliated with OpenAI, Tibo, or Codex Reset. A reset or credit announcement does not confirm that an individual Codex account has received a refill.

## Install and use

1. Add `widget.owl` to the Omarchy widget store or install it through your launcher.
2. Tap **中文** on the tile or in the full-screen view to switch to Chinese; tap **English** to return. The selected language is saved on the device.
3. Use **My quota** to refresh the local account snapshot. Use **Check updates** to request the public monitor data; API cooldowns still apply.
4. Select a calendar date to view cached events. Calendar navigation does not trigger a quota scan or API request.

The quota scanner uses Python's standard library and reads `~/.codex/sessions`. Public event dates are grouped in Beijing time; local quota timestamps use device time. If API requests fail or the source marks its feed stale, the widget labels the data as delayed and continues to show the last valid response.

The widget requests only the data needed to render it. It does not upload local quota values, session files, or account credentials.

## Replacing the older editions

Install this unified widget, confirm that it appears on the home screen, then remove the separate English and Chinese quota widgets so you do not keep duplicate monitors.

## Source

- [Codex Reset API documentation](https://codex-reset.com/developers)
- [Public feed](https://codex-reset.com/api/feed)
- [Public timeline](https://codex-reset.com/api/timeline)
