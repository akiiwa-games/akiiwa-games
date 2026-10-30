<div align="center">

# 🧭 [AgentCompass](https://github.com/akiiwa-games/AgentCompass)

**Match each task to the right model, effort and subscription quota. Decided by arithmetic, not habit.**<br>
**让每个任务匹配合适的模型、推理强度与订阅额度:靠算术决定,不靠感觉。**

[![AgentCompass](https://raw.githubusercontent.com/akiiwa-games/AgentCompass/main/docs/hero.gif)](https://github.com/akiiwa-games/AgentCompass)

</div>

## Why / 为什么做

| Problem · 痛点 | AgentCompass |
|---|---|
| **Every agent has a different edge.** Treating models as interchangeable wastes their best traits.<br>**各擅所长**:一视同仁,难题啃不动,杂活用大炮。 | Five-dimension task profile + model DNA fit pick the *minimum-sufficient* model and effort.<br>五维任务画像 + 模型 DNA,按“最小够用”匹配模型与强度。 |
| **Decision fatigue.** Provider, account, tier, effort, dozens of times a day.<br>**选择疲劳**:每天几十次在账号、档位、强度间权衡。 | One command: `roll`. The router classifies, allocates, records and launches.<br>一条命令 `roll`:分类、分配、记账、启动。 |
| **Quota chaos.** One account hits the wall while another's weekly window expires unused.<br>**额度混乱**:主力号撞墙,另一个订阅白白过期。 | Live 5h / 7d windows in USD, pre-reset spend-down, 2M-token worker rotation, and a `PreToolUse` spawn gate that enforces the route.<br>实时 5h/7d 余量、重置前花完、2M 上下文轮换,并由 `PreToolUse` 门禁强制执行。 |

## What it covers / 覆盖范围

- **Hosts / 宿主**: Claude Code · Codex CLI · Google Antigravity (`agy`) · Paseo · Pi · OpenCode · **Orca** · **T3 Code**
- **Plans / 套餐**: built-in calibrated templates for Claude `Pro` / `Max 5x` / `Max 20x`, ChatGPT / Codex `Plus` / `Team` / `Pro 100` / `Pro`, Google AI `Pro` / `Ultra 5x` / `Ultra 20x`; extra accounts are discovered automatically.<br>内置经实测校准的套餐容量模板,多账号自动发现。
- **Windows cockpit / 驾驶舱**: 5-axis decision radar, ledger replay, dry-run simulator, model settings with background CLI auto-update.<br>五维决策雷达、账本回放、沙盘推演、后台自动更新。
- **[usage-float](https://github.com/akiiwa-games/usage-float)**: live quota HUD with one-click redemption of official rate-limit reset credits.<br>实时额度悬浮窗,一键兑换官方限流重置额度。

## 30 seconds / 30 秒上手

```bash
# Offline demo, nothing to configure / 离线演示,无需配置
git clone https://github.com/akiiwa-games/AgentCompass.git && cd AgentCompass
python -X utf8 skills/agent-compass/scripts/route_judge.py plan --input examples/task.json --dry-run --demo

# Install and onboard (Python 3.11+) / 安装并引导
uv tool install "git+https://github.com/akiiwa-games/AgentCompass"
agentcompass setup && agentcompass doctor
```

Windows: grab `AgentCompass-tray-setup.exe` from [Releases](https://github.com/akiiwa-games/AgentCompass/releases) (no admin rights). · Windows 用户可直接下载免管理员安装包。

## More / 更多

- [AgentCompass](https://github.com/akiiwa-games/AgentCompass): the router, spawn gate and cockpit / 路由器、门禁与驾驶舱
- [usage-float](https://github.com/akiiwa-games/usage-float): subscription quota HUD and collector / 订阅额度悬浮窗与采集器
- [lark-mbti-jev](https://github.com/akiiwa-games/lark-mbti-jev): local Feishu/Lark MBTI and anime persona overlay / 飞书 MBTI 与二次元人格叠加层
