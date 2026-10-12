# Codex Quota and Resets

Author: **9G420** · License: **MIT** · Version: **1.2.0**

A resizable Codex quota and public reset monitor for Omalauncher. Choose `codex-quota-en` for English or `codex-quota-zh` for Simplified Chinese. Both editions can be installed, using different widget filenames.

## Features

- Remaining 5-hour and weekly quota percentages from local Codex CLI records.
- Estimated reset countdowns and notifications at recorded reset times.
- Public Tibo reset announcements, original-post links and reset-credit information.
- A monthly reset calendar, daily records and 90-day reset statistics.
- A green indicator for unread changes to a public direct-reset announcement.
- A compact layout for smaller home-screen tiles and a full-screen detail view.

## Requirements and installation

Install from the widget store after review, or put `widget.owl` in `~/.config/omalauncher/widgets/` under a unique filename. Requires OWL 5, the launcher's initialized Linux environment and the Arch `python` package. Both Python sources are embedded in this file; no helper scripts or Python packages need to be downloaded.

For **your account quota**, install and sign in to Codex CLI separately, then use it on this device. The widget reads recent `token_count` / `rate_limits` records from `~/.codex/sessions`. If there are no usable records, it shows a pending value. It does not contact a private account API or read authentication files.

## Data and behavior

The quota source checks every minute; the public monitor checks every ten minutes. Percentages reflect the latest available local record and may lag the account. A countdown reaching zero does not imply a refill: the percentage becomes unknown until a newer record confirms the window. This widget does not grant quota or reset an account.

Public reset information is fetched anonymously from `https://aihot.news/codex-reset` and its daily-record endpoint. AIHOT is an unofficial aggregator; original-post links are supplied for verification. Public reset-calendar dates use Beijing time (UTC+8); account reset timestamps are displayed in the device timezone. A reset credit or general announcement does not prove that a particular account has refilled. Public titles, original post text and source audience/stage descriptions retain their source language. Announcement and fetch timestamps, like account reset timestamps, are displayed in the device timezone.

Each edition writes its own quota snapshot and public-monitor cache under `~/.cache/codex-quota-community/`. The widget's acknowledgement states are stored by the launcher. No login credentials, private conversations, personal quota values or device files are bundled with the widget or sent to the monitor. Parsing depends on Codex CLI's record format and AIHOT's page schema; changes may require an update. Monitor fetch failures retain cached records and show a stale status.
