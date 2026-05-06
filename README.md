# threads-yunwei-va

**VA 美容诊所（브이에이성형외과·피부과）专属 Threads 全AI驱动自动运营 Skill**

基于 [threads-yunwei](https://github.com/gaojiongwenv587-beep/threads-yunwei-skill) 通用版定制，内置 VA 诊所完整知识库、真实运营数据沉淀和月度分析报告。Claude 作为决策大脑，从抓取到评论到记忆进化全程自主运行。

---

## 账号现状（截至 2026-05-06）

| 指标 | 数值 |
|------|------|
| 账号 | @vaclinic.korea |
| 运营天数 | D=42 |
| 粉丝数 | 211 |
| 累计评论 | 360+ 条 |
| 当前模式 | 降频保护（关联账号4/30被封，保守运营中）|
| 日均粉丝增长 | ~1.1 人/天 |

---

## 与通用版的区别

| 对比项 | threads-yunwei（通用版）| threads-yunwei-va（本版）|
|--------|------------------------|--------------------------|
| 知识库 | 需手动配置 | ✅ 内置价格表 + 白皮书 + 运营洞察 + 月报 |
| 账号定位 | 需向导填写 | ✅ 预置 VA 诊所定位模板和关键词矩阵 |
| 运营策略 | 空白起步 | ✅ D=42 实战沉淀，含踩坑记录 |
| 知识库加载 | 启动时需手动 | ✅ PHASE -1 三步强制自动读取 |
| 安装向导 | 5步 | ✅ 4步（知识库步骤已内置跳过）|

---

## 内置知识库

| 文件 | 内容 | 更新时间 |
|------|------|---------|
| `references/va-prices.md` | VA 诊所完整价格表（6大类，中韩对照，含+10%税说明，TWD换算）| 2026-05-06 |
| `references/va-whitepaper.md` | VA 皮肤科·整外白皮书（院长金長龍，梨花女大教授，建院21年）| 2026-04-01 |
| `references/va-operational-insights.md` | 运营策略+热点话题+评论战术+踩坑记录+周度分析 | 2026-05-06 |
| `references/va-monthly-report-april.md` | 4月运营月报（D=7~D=36，数据+分析+5月目标）| 2026-05-06 |

---

## 运营流程

```
PHASE -1   AI 自检
             Step A: 读取 references/ 所有知识库文件
             Step B: 读取 memory/ 记忆文件
             Step C: 读取当前策略/会话/KPI
Phase 0    启动检查 + 断点续传 + Chrome 验证
Phase 0.5  效果回溯（检查 24-72h 前评论互动）
Phase 1    三源抓取（Feed 50 + 关键词搜索 + 对标账号 ≈ 600 条）
Phase 2    热度评分 + AI 筛选 + 策略更新
Phase 3    灵活发帖（AI 决定是否发、发什么）
Phase 4    精准评论（AI 两阶段筛选，15-30 条/日）
Phase 5    账号成长监控 + 日志
Phase 6    三层记忆更新（daily / weekly / longterm）
```

---

## 依赖

| 依赖 | 版本 | 说明 |
|------|------|------|
| [threads-skill](https://github.com/openclaw/threads-skills) | latest | Threads CLI，基于 Chrome CDP 控制浏览器 |
| Claude | claude-sonnet-4-6+ | 决策引擎，内容生成，数据分析 |
| Python | 3.8+ | threads-skill 运行环境 |
| Google Chrome | 任意版本 | 需以调试模式启动 |

---

## 快速开始

### 1. 安装 threads-skill

```bash
cd /path/to/threads-skills
uv run python scripts/cli.py --help   # 验证安装
```

### 2. 安装本 Skill

```bash
openclaw skill install https://github.com/gaojiongwenv587-beep/threads-yunwei-va
```

或手动放置：将整个目录（含 `references/`）复制到 Claude Code 的 skills 目录。

> ⚠️ 必须保留 `references/` 目录，知识库文件是 Skill 运行的核心上下文。

### 3. 启动 Chrome

```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome \
  --remote-debugging-port=8666 \
  --user-data-dir="/path/to/chrome-profile" \
  --no-first-run
```

### 4. 触发运营

```
执行今日运营
帮我运营一下 Threads
```

**首次运行**触发 4 步安装向导：
```
Step 1/5  确认 threads-skill 路径
Step 2/5  AI 配置（默认 Claude）
Step 3/5  选择运营账号
Step 3.5  账号定位（VA 诊所预置模板可参考）
Step 4/5  ✅ 自动跳过（内置知识库）
Step 5/5  对标账号文档（可跳过）
```

---

## 安全说明

敏感信息**绝不**存入本仓库：

| 存储位置 | 内容 | 是否公开 |
|---------|------|---------|
| 本仓库 `SKILL.md` | 账号定位、关键词等非敏感配置 | ✅ 公开 |
| `~/.threads/yunwei_secrets.json` | API Key | ❌ 仅本地 |
| `~/.threads/accounts/` | Chrome Profile / Cookie | ❌ 仅本地 |

详见 [SECURITY.md](./SECURITY.md)

---

## 当前热点话题（2026-05 实测）

| 话题 | 互动参考 | VA 切入点 |
|------|---------|---------|
| onda + 溶脂针 | 2119回（观测帖）| VA 有 onda 40/60/80kj + 溶脂针 |
| 韩音波对比 | 52赞/18回 | VA 有 Shrink/Ulthera/Density/Trinity 全线 |
| 5月赴韩医美 | 多帖 30+ 回 | 5-6月旅游旺季，真实买家 |
| 台湾 vs 韩国价格 | 持续高热 | TWD 换算格式已验证有效 |

---

## 更新日志

详见 [CHANGELOG.md](./CHANGELOG.md)

当前版本：**v1.2.0**（2026-05-06）

---

## License

[MIT](./LICENSE)
