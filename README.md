# OpenClaw Workflow Analyzer — 分析工作流程的自动化可行性

> 把你的日常工作拆解为可自动化的子流程，评估 OpenClaw 实现难度，给出先易后难的落地路径。

[![ClawHub](https://img.shields.io/badge/ClawHub-openclaw--workflow--analyzer-blue)](https://clawhub.ai/fangshan101-coder/openclaw-workflow-analyzer)
[![Version](https://img.shields.io/badge/version-1.0.0-green)](https://clawhub.ai/fangshan101-coder/openclaw-workflow-analyzer)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Why

想用 AI Agent 自动化工作流，但不知道：

- 哪些环节**真的能**自动化，哪些只是看起来能
- 第三方数据到底拿不拿得到（有 API？要登录？在内网？）
- 应该从哪一步开始，投入产出比最高

**Workflow Analyzer 不帮你执行自动化，而是帮你看清全局——哪些能做、多难、先做哪个。**

## 安装

```bash
npx clawhub@latest install fangshan101-coder/openclaw-workflow-analyzer
```

## 快速开始

```
"分析一下我的日常工作流程，看看哪些能自动化"
"我每天要做 X、Y、Z，OpenClaw 能帮我做哪些"
"帮我分析这个流程的自动化可行性"
```

## 工作流程

### 1. 输入模式自适应

- **引导式**：你没有完整描述时，用苏格拉底式提问逐步挖掘
- **直接分析**：你已提供完整流程，直接进入拆解

### 2. 流程拆解

将工作流拆为树状结构，每个子流程是可独立判断的最小有意义单元：

```
大流程：每日数据报告
├── 子流程 1：从飞书拉取数据
├── 子流程 2：数据清洗合并
├── 子流程 3：生成可视化图表
└── 子流程 4：发送到钉钉群
```

### 3. 第三方数据确认

涉及外部数据时**主动确认**，不做假设：

- 有 API 接口吗？
- 需要认证吗？有凭证吗？
- 网络可达吗（公网/VPN/内网）？

### 4. 难度评级（⭐1-10 星）

面向小白视角的难度阶梯：

| 难度 | 你需要做什么 | 打个比方 |
|------|-------------|---------|
| ⭐ | 直接用，打字就行 | 像跟朋友聊天 |
| ⭐⭐ | 注册账号，填密钥 | 像注册 App |
| ⭐⭐⭐ | 写一份"说明书" | 像写工作交接文档 |
| ⭐×4-5 | 接 API + 数据处理 | 像写复杂 Excel 公式 |
| ⭐×6-7 | 网页爬取/模拟操作 | 像远程控制电脑 |
| ⭐×8-10 | 控制手机/开发新能力/对接硬件 | 像开发新 App |
| ⚫ | 做不了 | 数据拿不到 |

### 5. 输出报告

```
📋 工作流分析：每日数据报告

| 子流程 | 实现路径 | 难度 | 第三方依赖 |
|--------|---------|------|-----------|
| 拉取数据 | Skill+API | ⭐×4 | 飞书 API (有) |
| 数据清洗 | Skill+脚本 | ⭐×5 | 无 |
| 生成图表 | 开箱即用 | ⭐×1 | 无 |
| 发送钉钉 | Skill+Webhook | ⭐⭐ | 钉钉 Webhook (有) |

💡 落地建议（先易后难）：
1. 先搞定"生成图表" → 立刻体验价值
2. 再接"发送钉钉" → 学 Webhook 配置
3. 最后攻"拉取数据+清洗" → 学 API 对接
```

## 不适用场景

- 直接执行自动化任务（本 Skill 只做分析和建议）
- 非 OpenClaw 平台的自动化评估
- 具体 Skill 编写（请使用 skill-creator）

## 兼容性

- Claude Code (CLI)
- Claude.ai (Web)
- API

## License

MIT
