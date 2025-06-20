# RobinHood Project Blacklist Format

[简体中文](README.md)

This document describes the JSON format for the RobinHood Project blacklist, used to record banned players' information, including UUID, ban reason, and related metadata.

## JSON Structure

```json
{
    "blacklist": [
        {
            "uuid": "<player-uuid>",
            "reason_id": "<reason-code>",
            "reason_original": "<detailed-reason>",
            "submitted_by": "<submitter-id>",
            "ban_timestamp": "<unix-timestamp>"
        }
    ]
}
```

### Field Descriptions

| Field              | Type   | Description                                                  |
|--------------------|--------|--------------------------------------------------------------|
| `uuid`             | String | Player's unique identifier (UUID) for identification.         |
| `reason_id`        | String | Code for the ban reason, facilitating categorization.         |
| `reason_original`  | String | Detailed description of the ban reason and violation context. |
| `submitted_by`     | String | Server name that submitted the ban, for tracking purposes.    |
| `ban_timestamp`    | String | Unix timestamp (seconds) when the ban was issued.             |

### Example

```json
{
    "blacklist": [
        {
            "uuid": "123e4567-e89b-12d3-a456-426614174000",
            "reason_id": "game_cheat",
            "reason_original": "Using cheat clients in gameplay",
            "submitted_by": "RHP-TestServer",
            "ban_timestamp": "1750408200"
        },
        {
            "uuid": "234e5678-e89b-12d3-a456-426614174001",
            "reason_id": "chat_spam",
            "reason_original": "Sending excessive spam messages in server chat",
            "submitted_by": "RHP-TestServer",
            "ban_timestamp": "1750408200"
        },
        {
            "uuid": "345e6789-e89b-12d3-a456-426614174002",
            "reason_id": "game_pvp_tk",
            "reason_original": "Maliciously attacking teammates in PVP server",
            "submitted_by": "RHP-TestServer",
            "ban_timestamp": "1750408200"
        }
    ]
}
```

### Common Reason IDs

See [Ban Reason Codes](ReasonID_en.md)

### Notes

1. **UUID Format**: Must be a valid Minecraft UUID.
2. **Timestamp**: `ban_timestamp` uses Unix timestamp (seconds), e.g., `1750408200` for 2025-06-20 09:30:00 UTC.
3. **Permanent Bans**: All bans are permanent by default, with no expiration. Refer to the project homepage for appeal options.
```
