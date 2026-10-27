# Why I Built [AgentCompass](https://github.com/akiiwa-games/AgentCompass)

When you live inside coding agents all day—running Claude Code, Codex, Antigravity, Grok, and local runners side by side—the bottleneck stops being *"can AI write this code?"* and becomes **orchestration friction**.

**[AgentCompass](https://github.com/akiiwa-games/AgentCompass)** grew out of three daily pain points that kept breaking my flow:

---

### 1. Every Agent Has a Different Edge · Agent 各擅所长
No single model wins every task anymore:
- One model is unmatched at **deep root-cause debugging** across tangled state and race conditions;
- Another shines at **divergent architecture, product copy, and UI direction**;
- Another is a fast, surgical workhorse for **bounded refactors and test loops**;
- Another runs in a **free isolated sandbox** that shouldn't even touch local machine quota.

Treating every subagent call as homogeneous either under-powers hard problems or wastes a specialist on boilerplate.

### 2. Model & Effort Decision Fatigue · 模型选择疲劳
Every time a task branches into sub-tasks, you face the same micro-tax:
> *"Which provider should run this? Which account? Which model tier? Should effort be `low`, `medium`, `high`, or `xhigh`?"*

Making that decision manually dozens of times a day leads to two bad outcomes: you either burn mental energy babysitting model pickers, or you lazily leave your most expensive flagship model on `xhigh` for everything—including 3-minute chores.

### 3. Multi-Subscription Quota Chaos · 额度管理困难
Heavy agent workflows rarely fit inside a single subscription. Once you juggle multiple rolling 5-hour windows, 7-day caps, weekly model pools, and staggered reset clocks across providers:
- One account hits a sudden **rate-limit wall mid-sprint** while you are deep in context;
- Meanwhile, another paid subscription sits idle and **lets 60% of its weekly capacity expire unused** at reset time.

---

## The Thesis: Route Work by Math, Not Guesswork

**[AgentCompass](https://github.com/akiiwa-games/AgentCompass)** turns *"who should do this task?"* from a human habit into a **deterministic, auditable routing step**:

1. **5D Task Profiling (System-One)**: Scores the task itself (`code_complexity`, `reasoning_depth`, `context_scale`, `tool_loop_intensity`, `hallucination_risk`) without hardcoding model names.
2. **Minimum-Sufficient Capability Fit**: Matches the task vector against each model+effort bundle's actual strengths—never under-provisioning high-risk work, never over-spending `xhigh` on simple loops.
3. **Reset-Aware Quota Pacing**: Reads live remaining capacity and reset horizons (powered by [usage-float](https://github.com/akiiwa-games/usage-float)) to balance burn rates across accounts before windows reset.
4. **Hard Gate Enforcement**: Hooks into `PreToolUse` / `tool_call` so main sessions cannot silently spawn unrouted or under-configured subagents.

[![AgentCompass overview](https://raw.githubusercontent.com/akiiwa-games/akiiwa-games/main/assets/agentcompass.png)](https://github.com/akiiwa-games/AgentCompass)

```powershell
git clone https://github.com/akiiwa-games/AgentCompass.git
cd AgentCompass
python -X utf8 skills/route-agent-work/scripts/route_judge.py plan --input examples/task.json --dry-run --demo
```
*(Runs offline with synthetic multi-account quota data—no API keys or live credentials required.)*
