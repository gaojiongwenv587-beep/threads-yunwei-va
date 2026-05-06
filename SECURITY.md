# Security Policy

## 敏感信息处理

本 Skill 设计时已将敏感信息与非敏感配置严格分离：

| 存储位置 | 内容 | 是否可公开 |
|---------|------|-----------|
| `SKILL.md`（本仓库） | 账号定位、关键词、知识库路径等非敏感配置 | ✅ 可公开 |
| `~/.threads/yunwei_secrets.json` | API Key、账号凭证 | ❌ 仅本地，绝不上传 |
| `~/.threads/accounts/` | Chrome Profile、登录 Cookie | ❌ 仅本地，绝不上传 |

## .gitignore 保护范围

以下文件类型已被 `.gitignore` 排除，即使误操作 `git add .` 也不会被提交：

```
*secrets*          # API Key、账号密码
*.env / .env.*     # 环境变量文件
yunwei_*.json      # 本地运营数据（策略、日志、校准等）
yunwei_*.md        # 本地运营报告
calibration-history.md
```

## 安装前注意事项

1. **不要将 `~/.threads/` 目录上传至任何公开仓库**
2. **不要将 Chrome Profile 目录（`~/.threads/accounts/`）分享给他人**
3. 运营数据（发帖记录、评论记录、粉丝数据）属于账号隐私，请勿公开

## Reporting a Vulnerability

如发现本 Skill 存在安全漏洞（例如可能导致凭证泄露的设计缺陷），请通过以下方式联系：

- 提交 [GitHub Issue](../../issues)，标题前缀加 `[SECURITY]`
- 请勿在 Issue 中直接附上真实凭证或账号信息

## 免责声明

本 Skill 用于 Threads 账号运营自动化，使用者需自行遵守 Threads 平台使用条款。因违反平台规则导致的账号封禁，本项目不承担责任。
