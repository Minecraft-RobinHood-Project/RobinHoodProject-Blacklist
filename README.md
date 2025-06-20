# RobinHood Project Blacklist Format

[English Version](README_en.md)

本文件描述了 RobinHood Project 黑名单的JSON格式，用于记录被封禁玩家的信息，包括UUID、封禁原因及相关数据

## JSON 结构

```json
{
    "blacklist": [
        {
            "uuid": "<玩家UUID>",
            "reason_id": "<原因代号>",
            "reason_original": "<详细原因>",
            "submitted_by": "<提交者ID>",
            "ban_timestamp": "<Unix时间戳>"
        },
        ...
    ]
}
```

### 字段说明

| 字段              | 类型   | 描述                                                       |
|-------------------|--------|------------------------------------------------------------|
| `uuid`            | 字符串 | 玩家唯一标识符（UUID），用于识别玩家 |
| `reason_id`       | 字符串 | 封禁原因的代号，便于分类和快速识别                   |
| `reason_original` | 字符串 | 封禁原因的详细描述，说明具体违规行为                     |
| `submitted_by`    | 字符串 | 提交封禁的服务器名称，用于追踪来源   |
| `ban_timestamp`   | 字符串 | 提交封禁时间的Unix秒级时间戳         |

### 示例

```json
{
    "blacklist": [
        {
            "uuid": "123e4567-e89b-12d3-a456-426614174000",
            "reason_id": "game_cheat",
            "reason_original": "使用作弊客户端进行游戏",
            "submitted_by": "RHP-TestServer",
            "ban_timestamp": "1750408200"
        },
        {
            "uuid": "234e5678-e89b-12d3-a456-426614174001",
            "reason_id": "chat_spam",
            "reason_original": "在服务器内发送大量垃圾信息刷屏",
            "submitted_by": "RHP-TestServer",
            "ban_timestamp": "1750408200"
        },
        {
            "uuid": "345e6789-e89b-12d3-a456-426614174002",
            "reason_id": "game_pvp_tk",
            "reason_original": "在PVP服务器中恶意攻击队友",
            "submitted_by": "RHP-TestServer",
            "ban_timestamp": "1750408200"
        }
    ]
}
```

### 常用原因代号

请查看 [封禁代号列表](ReasonID.md)

### 注意事项

1. **UUID格式**：必须为有效的 Minecraft 正版 UUID
2. **时间戳**：`ban_timestamp` 使用Unix时间戳（秒），如 `1750408200` 表示2025-06-20 09:30:00 UTC
3. **永久封禁**：默认所有封禁为永久封禁，无到期时间，可参考项目主页申诉解封
