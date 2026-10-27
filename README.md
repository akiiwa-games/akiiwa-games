# Why [AgentCompass](https://github.com/akiiwa-games/AgentCompass)

When you work with multiple coding agents every day, the bottleneck is no longer writing code—it is deciding **who runs what, at what effort, on which subscription**.

**[AgentCompass](https://github.com/akiiwa-games/AgentCompass)** is built to solve three recurring problems:

- **Every agent has a different edge**: One model excels at deep root-cause debugging, another at system design and copy, another at fast bounded refactors, and another in a free isolated sandbox. Treating them as interchangeable wastes their best traits.
- **Model & effort decision fatigue**: Choosing a provider, account, model tier, and effort level (`low` / `medium` / `high` / `xhigh`) dozens of times a day either drains your focus or leaves your most expensive flagship model burning `xhigh` on three-minute chores.
- **Multi-subscription quota chaos**: Across rolling 5-hour windows, weekly caps, and staggered reset clocks, one account hits a rate limit mid-sprint while another paid subscription lets half its capacity expire unused.

**The fix**: Score the task across five dimensions, match the minimum-sufficient model and effort, pace live quota before each window resets (via [usage-float](https://github.com/akiiwa-games/usage-float)), and enforce the route at `PreToolUse`.

[![AgentCompass](https://raw.githubusercontent.com/akiiwa-games/akiiwa-games/main/assets/agentcompass.png)](https://github.com/akiiwa-games/AgentCompass)

```powershell
git clone https://github.com/akiiwa-games/AgentCompass.git
cd AgentCompass
python -X utf8 skills/route-agent-work/scripts/route_judge.py plan --input examples/task.json --dry-run --demo
```

---

# 为什么做 [AgentCompass](https://github.com/akiiwa-games/AgentCompass)

每天并行使用多个 Coding Agent 时，真正的瓶颈不再是“写不写得出代码”，而是**谁来跑、开多高推理强度、花哪个账号的额度**。

**[AgentCompass](https://github.com/akiiwa-games/AgentCompass)** 只解决三件事：

- **Agent 各擅所长**：有的模型擅长复杂深水区排障，有的擅长发散架构与文案设计，有的适合快速局部改码，有的适合在免费独立沙箱里跑闭环。把所有子任务一视同仁，要么难题啃不动，要么拿大炮打蚊子。
- **模型选择疲劳**：每次拆分子任务都要在提供商、账号、模型档位和推理强度（`low` / `medium` / `high` / `xhigh`）之间反复权衡；一天做几十次选择，不是精力耗尽，就是把 3 分钟的杂活全挂在最贵的旗舰模型上空烧。
- **额度管理困难**：多个 5 小时滚动窗口、周限额与不同重置时间交织在一起，常常主力号在冲刺中途撞墙限流，另一个付费订阅却在重置时白白浪费掉大半额度。

**解法**：对任务做五维画像，按“最小够用能力”匹配模型与推理强度，结合 [usage-float](https://github.com/akiiwa-games/usage-float) 的实时余量与重置倒计时动态配速，并通过 `PreToolUse` 门禁强制落地。
