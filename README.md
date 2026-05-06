# threads-yunwei-va

**VA 美容诊所（브이에이성형외과·피부과）专属 Threads 自动运营 Skill**

基于 [threads-yunwei](https://github.com/gaojiongwenv587-beep/threads-yunwei-skill) 通用版，针对 VA 诊所定制，内置完整知识库和运营策略沉淀。

---

## 与通用版的区别

| 对比项 | threads-yunwei（通用版） | threads-yunwei-va（本版） |
|--------|------------------------|--------------------------|
| 知识库 | 需手动配置 | ✅ 内置 VA 完整价格表 + 白皮书 |
| 账号定位 | 需向导填写 | ✅ 预置 VA 诊所定位模板 |
| 运营策略 | 空白起步 | ✅ 附带 D=26 天实战沉淀 |
| 关键词矩阵 | 需自填 | ✅ 预置 VA 医美关键词库 |

---

## 内置知识库

| 文件 | 内容 |
|------|------|
| `references/va-prices.md` | VA 诊所完整价格表（中韩对照，含 +10% 税说明）|
| `references/va-whitepaper.md` | VA 皮肤科·整外白皮书（院长介绍、主推项目详情）|
| `references/va-operational-insights.md` | 运营策略沉淀（高热话题、内容方向、评分模型校准状态）|

---

## 依赖

| 依赖 | 说明 |
|------|------|
| [threads-skill](https://github.com/openclaw/threads-skills) | Threads CLI 工具，基于 Chrome CDP 控制浏览器 |
| Claude（claude-sonnet-4-6+） | 决策引擎，内容生成，数据分析 |
| Python 3.8+ | threads-skill 运行环境 |
| Chrome | 已启动调试模式 |

---

## 快速开始

### 1. 安装 threads-skill

```bash
cd /path/to/threads-skills
. .venv/bin/activate
python scripts/cli.py --help
```

### 2. 安装本 Skill

```bash
openclaw skill install https://github.com/gaojiongwenv587-beep/threads-yunwei-va
```

或手动放置：将整个目录（含 `references/`）复制到 Claude Code 的 skills 目录。

### 3. 首次运行

触发方式：
```
执行今日运营
帮我运营一下 Threads
```

首次运行会触发 4 步向导（知识库步骤已自动跳过，比通用版少一步）：
```
Step 1/5  确认 threads-skill 路径
Step 2/5  AI 配置
Step 3/5  选择运营账号
Step 3.5  账号定位（有 VA 诊所预置模板可参考）
Step 4/5  ✅ 自动跳过（内置知识库已加载）
Step 5/5  对标账号文档（可跳过）
```

---

## 运营流程

```
Phase 0    启动检查 + 断点续传 + Chrome 验证
Phase 0.5  效果回溯（检查 24-72h 前评论的实际互动）
Phase 1    三源抓取（Feed 50 + 关键词 20×20 + 对标账号×15 ≈ 600 条）
Phase 2    热度评分 + AI 筛选 + 策略更新
Phase 3    灵活发帖（AI 决定是否发、发什么）
Phase 4    精准评论（AI 两阶段筛选，20-30 条/日）
Phase 5    账号成长监控 + 日志
Phase 6    三层记忆更新（daily / weekly / longterm）
```

---

## 已知运营背景

- 账号 @vaclinic.korea，创建于 2026-03-25
- 建院21年（2005年），首尔新沙站4号出口
- 目标受众：考虑赴韩整形的华语用户（台湾、大陆、海外华人）
- 高热话题：术后效果分享、台湾 vs 韩国价格对比、敏感肌医美、男性医美
- 当前评分权重：热度 40% + 相关性 35% + 时效 25%

---

## License

MIT
