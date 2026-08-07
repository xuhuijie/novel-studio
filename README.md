# Novel Studio

小说创作全流程工作台。集成记忆管理、写作技法与流程控制，覆盖从规划、创作、检验到备份的全链路。

## 核心能力

- **记忆管理**：多作品并行管理、伏笔追踪（P1/P2/P3）、章节逻辑六维度检验
- **写作技法**：草蛇灰线、虚实相生、诗化语言、对话机锋、双线镜像、倒推大纲
- **流程控制**：章节备份、压缩脚本、逻辑检验报告、人物状态追踪

## 目录结构

```
novel-studio/
├── SKILL.md                      # 主技能文件
├── references/                   # 专项工具
│   ├── character-template.md     # 人物小传模板
│   ├── foreshadowing-checklist.md # 伏笔检查清单
│   ├── literary-devices.md       # 文学手法库
│   ├── pacing-guide.md           # 节奏指南
│   ├── system-progression.md     # 系统类设定指南
│   ├── english-remnant-scan.md   # 英文残留扫描指南
│   └── inspection-report-template.md # 检验报告模板
├── templates/                    # 可复用模板
│   ├── chapter-backup-template.md # 章节备份模板
│   └── memory-file-template.md   # 记忆文件模板
└── scripts/                      # 工具脚本
    ├── compress_novel_memory.py  # 记忆文件压缩（Python）
    └── compress_novel_memory.sh  # 记忆文件压缩（Shell）
```

## 环境路径

| 用途 | 路径 |
|------|------|
| 记忆文件 | `/home/agent/.hermes/memory/novels/{小说名}.md` |
| 章节备份 | `/home/agent/.hermes/novels/{小说名}/chapters/` |
| 伏笔追踪 | 记忆文件内 P1/P2/P3 分级 |
| Git 仓库 | 记忆文件目录，建议 Git 管理 |

## 使用场景

### 1. 从零开始创作

输入「开始创作」「写一部新小说」，技能将引导你完成：
- 极简问询（最多3问：题材/主题/主角）
- 自动脚手架：记忆文件 + 第1章 + 本地备份
- 系统类小说：第1章内激活系统并可见，避免后期战力崩坏

### 2. 续写已有章节

输入「续写《书名》第N章」，技能将：
- 读取记忆文件，核对伏笔/人物/时间线
- 技法选型（草蛇灰线/诗化语言/张弛有度等）
- 完成章节后自动执行逻辑检验 + 文笔打磨 + 更新记忆

### 3. 多人协作

- 记忆文件纳入 Git 管理
- 协作者通过 `git pull/push` 同步
- 自动检测冲突并标记

### 4. 多作品并行

- 每部小说独立记忆文件
- 独立章节备份目录
- 随时切换当前工作作品

## 核心流程

```
1. 读取记忆文件
2. 技法选型
3. 创作章节
4. 逻辑检验（六维度）
5. 文笔打磨
6. 更新记忆 + 本地备份
```

## 伏笔管理

| 优先级 | 含义 | 示例 | 检验频率 |
|--------|------|------|----------|
| P1 | 核心悬念，影响主线 | 主角真实身份、最终BOSS | 每章必检 |
| P2 | 重要线索，影响支线 | 父亲下落、配角秘密 | 每3章检查 |
| P3 | 细节呼应，锦上添花 | 物品去向、小角色命运 | 每10章检查 |

## 记忆文件压缩

当记忆文件超过 2000 字或 20 章概要时，运行压缩脚本：

```bash
# Python 版本（功能更完整）
python3 /home/agent/.hermes/skills/novel-studio/scripts/compress_novel_memory.py \
  /home/agent/.hermes/memory/novels/{小说名}.md

# Shell 版本（无需 Python 环境）
bash /home/agent/.hermes/skills/novel-studio/scripts/compress_novel_memory.sh \
  /home/agent/.hermes/memory/novels/{小说名}.md
```

## 触发词

小说、章节、续写、人物设定、创建小说、世界观、伏笔、时间线、剧情概要、记忆文件压缩、备份章节、双线叙事、人物小传、草蛇灰线、诗化语言、硬核智斗、灰色人设

## 版本

v1.1.0

## 许可

MIT
