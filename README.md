# Akiiwa · tools for people who build with agents

**Route the work. See the quota. Make the desktop yours.**  
**把任务交给合适的 Agent，看清额度，也给桌面加一点自己的风格。**

I build local tools for coding-agent workflows and playful Windows interfaces. Start with an offline routing demo, a one-shot quota check, or a sample chat overlay.

我做面向重度 AI 用户的本机工具：任务路由、订阅额度监控，以及带一点动漫趣味的桌面交互。三个项目都公开源码，欢迎试用、提 Issue 或贡献改进。

[![AgentCompass](https://img.shields.io/github/stars/akiiwa-games/AgentCompass?style=flat&label=AgentCompass)](https://github.com/akiiwa-games/AgentCompass)
[![usage-float](https://img.shields.io/github/stars/akiiwa-games/usage-float?style=flat&label=usage-float)](https://github.com/akiiwa-games/usage-float)
[![lark-mbti-jev](https://img.shields.io/github/stars/akiiwa-games/lark-mbti-jev?style=flat&label=lark-mbti-jev)](https://github.com/akiiwa-games/lark-mbti-jev)

## 🧭 [AgentCompass](https://github.com/akiiwa-games/AgentCompass)

**Match each task to an eligible model and effort level across your AI subscriptions.** A Python `route-agent-work` skill ranks workers using task fit and quota windows; an optional `PreToolUse` gate checks routed launches. The Windows cockpit is optional. Alpha: adapt the reference fleet to your own accounts.

**按任务能力需求与订阅剩余额度选择 worker。** 核心是可审计的确定性路由器，支持 Claude Code、Codex、Antigravity、Grok 和 Paseo；可选门禁约束子 Agent 启动。

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB)](https://github.com/akiiwa-games/AgentCompass#try-it)
[![Agent Skill](https://img.shields.io/badge/Agent_Skill-route--agent--work-6750A4)](https://github.com/akiiwa-games/AgentCompass/tree/main/skills/route-agent-work)
[![License](https://img.shields.io/github/license/akiiwa-games/AgentCompass)](https://github.com/akiiwa-games/AgentCompass/blob/main/LICENSE)

[![AgentCompass preview](https://raw.githubusercontent.com/akiiwa-games/akiiwa-games/main/assets/agentcompass.png)](https://github.com/akiiwa-games/AgentCompass)

```powershell
git clone https://github.com/akiiwa-games/AgentCompass.git
cd AgentCompass
python -X utf8 skills/route-agent-work/scripts/route_judge.py plan --input examples/task.json --dry-run --demo
```

Offline, synthetic quota data; no credentials or worker launches. / 离线演示，不读凭据、不启动 worker。

## 📊 [usage-float](https://github.com/akiiwa-games/usage-float)

**Keep multi-account subscription quotas visible while you code.** A borderless Windows HUD and headless collector show usage windows and reset times for Claude, Codex, Grok, Antigravity and supported gateways. Inspect and redeem available reset credits from the HUD.

**多个账号的 5 小时与周额度，一眼看清。** 可独立运行，也为 AgentCompass 提供额度数据；支持悬浮窗、副屏面板与可用重置额度的查看和兑换。

[![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D4)](https://github.com/akiiwa-games/usage-float#installation--quick-start)
[![CLI + HUD](https://img.shields.io/badge/Interface-CLI_%2B_HUD-198754)](https://github.com/akiiwa-games/usage-float)
[![License](https://img.shields.io/github/license/akiiwa-games/usage-float)](https://github.com/akiiwa-games/usage-float/blob/main/LICENSE)

[![usage-float preview](https://raw.githubusercontent.com/akiiwa-games/akiiwa-games/main/assets/usage-float.png)](https://github.com/akiiwa-games/usage-float)

```powershell
git clone https://github.com/akiiwa-games/usage-float.git
cd usage-float
python usage_float.py once
# Windows + Python 3.10 with tkinter; launch the desktop HUD:
pythonw usage_float.py
```

Uses your local provider sign-ins; missing providers may show unavailable. For a standalone Windows package, see [Releases](https://github.com/akiiwa-games/usage-float/releases). / 使用本机已登录的账号；未登录的提供方可能显示不可用。

## 🎭 [lark-mbti-jev](https://github.com/akiiwa-games/lark-mbti-jev)

**Turn a Feishu/Lark chat into a local personality-themed desktop overlay.** Jev estimates MBTI probabilities from selected chat history; Windows UI Automation tracks name badges as the conversation scrolls. Optional anime character themes keep it playful. Labels are local; live analysis needs Lark permissions and a Jev/TypeSafe service.

**飞书群聊姓名旁的本机 MBTI / 动漫角色标签。** 概率仅供趣味参考，不是人格评估；标签不发送到群里。先渲染示例图即可体验视觉效果，无需聊天记录或 API 密钥。

[![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D4)](https://github.com/akiiwa-games/lark-mbti-jev#安装和启动)
[![Jev](https://img.shields.io/badge/Inference-TypeSafe_Jev-8B5CF6)](https://github.com/akiiwa-games/lark-mbti-jev)
[![License](https://img.shields.io/github/license/akiiwa-games/lark-mbti-jev)](https://github.com/akiiwa-games/lark-mbti-jev/blob/main/LICENSE)

[![lark-mbti-jev preview](https://raw.githubusercontent.com/akiiwa-games/akiiwa-games/main/assets/lark-mbti-jev.png)](https://github.com/akiiwa-games/lark-mbti-jev)

```powershell
git clone https://github.com/akiiwa-games/lark-mbti-jev.git
cd lark-mbti-jev
python -m pip install Pillow
python tools/render_demo.py
# Open docs/demo-mbti.png and docs/demo-girl-bands.png
```

Sample rendering only; no messages fetched and no model call. / 只生成示例图，不读取群聊、不调用模型。

---

**Try one, then tell me what got in your way.** Open an issue in the relevant repository; concrete examples and small improvements are welcome.  
**先试一个，卡在哪里就告诉我。** 欢迎在对应仓库提 Issue、反馈使用场景，或贡献一个小改进。
