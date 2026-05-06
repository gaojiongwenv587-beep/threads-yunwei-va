# Changelog

All notable changes to this project will be documented in this file.

## [1.2.0] - 2026-05-06

### Added
- `references/va-monthly-report-april.md` — 4月完整运营月报（D=7~D=36）
  - 发帖表现分析、评论战术效果、关键事件记录
  - 5月目标设定（粉丝250+，降频保护模式）
- `PHASE -1` 新增三步强制读取机制（Step A/B/C）
  - Step A：启动时自动读取所有 references/ 知识库文件
  - Step B：读取 memory/ 记忆文件
  - Step C：读取当前策略/会话/KPI JSON
  - 自检报告新增"知识库已读 N 个文件"输出

### Changed
- `references/va-operational-insights.md` — 全面更新至 D=42（2026-05-06）
  - 账号成长数据更新（211粉）
  - 当前策略：降频保护模式（关联账号4/30被封）
  - 热点话题更新：onda+溶脂针、5月赴韩、音波对比
  - 完整 TWD 换算价格表（30项）
  - 周度分析 W19（重启周）
  - 踩坑记录新增：情绪化发帖、关联账号封禁

---

## [1.1.0] - 2026-05-06

### Added
- Initial release as VA-specific skill, forked from `threads-yunwei` v1.0.0
- `references/va-prices.md` — VA 诊所完整价格表（6大类，中韩对照，含+10%税说明）
- `references/va-whitepaper.md` — VA 皮肤科·整外白皮书（院长金長龍介绍、主推项目）
- `references/va-operational-insights.md` — 初始运营策略沉淀（D=26天数据）

### Changed
- `SKILL.md` metadata: name → `threads-yunwei-va`, version → `1.1.0`, emoji → 🏥
- Step 4（知识库配置）：自动跳过，pre-bundle VA 知识库文件
- `KNOWLEDGE_FILES` 预填 `{SKILL_DIR}/references/` 下三个文件
- 标题由"Claude 全程驱动的自动运营系统"改为"VA 美容诊所专属 Threads 自动运营系统"

---

## [1.0.0] - 2026-03-25 *(upstream: threads-yunwei)*

Initial release of the generic `threads-yunwei` skill.

- 完整的 AI 驱动运营闭环（抓取→评分→发帖→评论→记忆→进化）
- 5步安装向导（threads-skill 路径 / AI配置 / 账号 / 账号定位 / 知识库 / 对标账号）
- 三层记忆系统（daily / weekly / longterm）
- 评分模型：互动×40% + 跨源×35% + 时效×25%，支持校准
- 断点续传机制（yunwei_session.json）
- 预热期自动降频保护
