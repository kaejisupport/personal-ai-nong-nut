# Long-Term Memory

## Technical Notes
### Telegram Group ID Issue in OpenClaw
- **Bug (Issue #40444)**: OpenClaw's newer versions (e.g., 2026.5.12) introduced a stricter validation logic for Telegram IDs, using a regex (`^\d+$`) that only accepts positive numbers. Telegram group IDs start with a minus sign (e.g., `-5200416075`), causing them to be incorrectly dropped as `not-allowed`.
- **Workarounds**:
  1. Set `groupPolicy: "allowall"` in the OpenClaw configuration (e.g. `openclaw.json` or gateway config). Note that this enables the bot in all groups it is added to.
  2. Fall back to Direct Messages (DM) since user IDs are positive numbers and pass the validation.