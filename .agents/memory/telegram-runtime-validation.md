---
name: Telegram runtime validation
description: Live worker checks depend on Telegram credentials being configured in the workspace.
---

The Telegram worker intentionally fails fast when API_ID, API_HASH, BOT_TOKEN, or ADMIN_ID is missing; keep this guard intact and use static checks until those values are configured.

**Why:** A missing-configuration run must not silently start a bot with invalid credentials or make a misleading persistence claim.

**How to apply:** For future runtime verification, configure the existing Telegram environment first, then restart the Telegram Bot Worker and inspect its logs.