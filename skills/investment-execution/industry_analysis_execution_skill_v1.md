---
name: industry_analysis_execution_skill
version: "1.0"
date: "2026-09-08"
type: "companion_execution_skill"
upstream_dependency:
  name: "industry_analysis_skill_v5"
  required_status: "FROZEN_BASELINE"
  required_sha256: "8f7d010183b8238fb6d0d21c2cf402a54c3ca7c2b4dfe464c41d25bde4be09f6"
primary_goal: "Translate frozen v5 research conclusions into disciplined position initiation, pyramiding, harvesting, re-underwriting, and exit actions without contaminating the research framework."
optimization_target: "Preserve v5 precision while maximizing capital allocation to evidence-confirmed asymmetric opportunities."
---

# Industry Analysis Execution Skill v1
## Companion Operating Guide for `industry_analysis_skill_v5`

---

# 0. Mission

本 Skill 不负责回答：

> “这个产业是不是 Day-27？”

也不负责回答：

> “这家公司是不是 HIGH-CONVICTION？”

这些判断全部由上游：

# `industry_analysis_skill_v5`

完成。

本 Skill 只负责把 v5 的研究输出转换成：

```text
WATCH
→ INITIATE
→ VALIDATE
→ PYRAMID
→ HOLD
→ HARVEST
→ EXIT
```

目标：

> **第一次 HIGH-CONVICTION 出现时不因等待“更确定”而错过赔率；当新证据进一步降低产业 / Winner 不确定性、且当前价格仍保留合理 forward 3× path 时加仓；当市场认知和估值追上基本面时收获，而不是被历史成本价或机械止盈规则支配。**

---

# 1. Constitutional Rule

研究与交易必须分层。

```text
RESEARCH LAYER
industry_analysis_skill_v5
        ↓
Classification / P1-P4
Expectation Gap
3× Underwriting
Tail Risk
Kill Criteria
Monitoring Dashboard
        ↓
EXECUTION LAYER
industry_analysis_execution_skill
        ↓
Position Action
```

## 禁止

本 Skill 不得为了支持已有持仓而修改 v5 结论。

不得：

```text
我已经持有
→ 所以重新解释 thesis

股价跌了
→ 所以把 UNDERWRITE 升级为 HC

股价涨了
→ 所以把 HC 自动降级

我成本很低
→ 所以忽略当前估值
```

---

# 2. Required Inputs from v5

每次执行至少需要：

```text
Company:
Research Date:
Specific S-Curve:
S-Curve Archetype:

Final Classification:
P1 = P(S-Curve inflects within 36m)
P2 = P(Top value-capture winner | inflection)
P3 = P(Market materially under-recognizes)
P4 = P(Forward 3× fundamental path)

Expectation Gap:
3× Fundamental Burden:
Tail-Risk Overlay:
Critical Vetoes:
Kill Criteria:
Monitoring Dashboard:
Strongest Counter-Thesis:

Current Price / Market Cap:
Current Position:
Externally Defined Max Position Budget:
```

其中：

> `Max Position Budget`

必须由用户 / portfolio policy 预先定义。

本 Skill 的 0%–100% 仓位比例，默认表示：

# **占该股票 Max Position Budget 的比例**

而不是整个投资组合的比例。

---

# 3. The Two-Clock Model

每只股票同时运行两个时钟。

## Clock A — Thesis Clock

跟踪：

```text
P1 — Industry timing
P2 — Winner certainty
P3 — Expectation gap
P4 — Forward 3× path
```

以及：

- Replication
- Demand Quality
- Value Capture
- Control Point
- Capital Reinforcement
- Platform Replication
- Tail Risk
- Kill Criteria

## Clock B — Position Clock

只决定：

- 是否建仓
- 建多少
- 是否加仓
- 是否减仓
- 是否退出

核心原则：

> **Thesis Clock 驱动 Position Clock，而不是股价走势驱动 Thesis Clock。**

---

# 4. Current Price Principle

所有新增 / 持有 / 卖出决策都必须从：

# **Current Price**

重新计算。

禁止把：

```text
Original Cost Basis
```

作为继续持有或卖出的核心依据。

每次问：

> **如果今天完全没有持仓，以当前价格重新运行 v5，我会不会买？**

如果答案变成 NO：

历史成本再低也不能自动构成 HOLD 理由。

---

# 5. Position State Machine

## State 0 — NO POSITION

适用于：

- TOO EARLY
- EMERGING
- INDUSTRY DAY-27
- AVOID
- INDUSTRY RIGHT / WINNER WRONG

默认：

```text
0% Max Position Budget
```

允许建立 Watchlist，不建立正式方向性仓位。

---

## State 1 — RESEARCH / UNDERWRITE

适用于：

- DAY-27 WATCH
- UNDERWRITE

默认：

```text
0–25% Max Position Budget
```

只有在用户明确允许 exploratory position 时使用。

目的：

- 保持 attention
- 跟踪 evidence
- 不把未通过 HC Gates 的 thesis 当成正式 conviction

禁止：

> 因“怕错过”把 UNDERWRITE 直接做成完整仓位。

---

## State 2 — INITIAL HC

第一次出现：

# HIGH-CONVICTION INVESTMENT DAY-27

且：

- 无 Critical Veto
- Expectation Gap = Positive
- 3× Burden = LOW / MODERATE
- Tail Risk 在可接受的 position sizing 范围内

默认目标：

# **50–70% Max Position Budget**

原则：

> 第一次 HC 就必须有实质仓位。

不能因为：

> “也许下一季度会更确定”

而只建立象征性仓位。

因为 HC 本身意味着：

> 当前 evidence 已经足够让错过机会的成本超过继续等待的收益。

---

## State 3 — VALIDATED HC

重大新证据出现，v5 Re-Underwriting 后：

```text
P1 ↑ and/or
P2 ↑
```

同时：

```text
P3 仍 Positive
P4 仍强
3× Burden 仍 LOW / MODERATE
No new Veto
```

典型 evidence：

- 第二/第三次 type-matched replication
- 新客户 / 新地域 / 新 workload
- model improvement → real customer economics
- production proof
- margin / unit economics证明
- control point strengthening
- next bottleneck resolution

默认目标：

# **70–90% Max Position Budget**

---

## State 4 — PYRAMID / SECOND DAY-27

如果出现：

- 同一 S-Curve 的关键 uncertainty 被消灭；
- 或新的 S-Curve 形成新的 Investment Day-27；
- 当前价格重新运行 v5 后仍为 HC；
- 3× Burden ≤ MODERATE；
- Tail Risk 未恶化到需要压低仓位；

则允许：

# **90–100% Max Position Budget**

这叫：

# **Pyramiding on Evidence**

不是：

> Price ↑ → Add

而是：

> **Evidence de-risking > Price rerating → Add**

---

# 6. Add Rule

只有以下条件全部成立才加仓：

```text
1. v5 Re-Underwriting = HC
2. P1/P2 至少一个实质增强，或新 S-Curve HC
3. P3 仍 Positive
4. P4 未明显下降
5. 3× Burden ≤ MODERATE
6. No Critical Veto
7. Tail-risk-adjusted position ≤ Max Position Budget
```

## 最重要的禁止规则

### 禁止因为跌价加仓

```text
Price ↓
≠
Evidence ↑
```

如果价格跌但：

- Structural KPI ↓
- Control Point ↓
- Demand Quality ↓
- P2 ↓

这是：

> thesis deterioration

不是加仓机会。

### 禁止因为上涨加仓

```text
Price ↑
≠
Evidence ↑
```

只有当基本面去风险速度超过价格重估速度时，才允许追涨。

---

# 7. De-Risking vs Re-Rating Test

每次考虑加仓时强制比较：

```text
Δ Fundamental Certainty
vs
Δ Market Recognition / Valuation
```

## Best Add Environment

```text
P1/P2 ↑↑
P3 still Positive
P4 intact
3× burden stable / improves
```

即：

# **De-risking > Re-rating**

## Bad Add Environment

```text
P1/P2 ↑
BUT
P3 ↓↓↓
3× burden HIGH / EXTREME
```

即：

# **Re-rating > De-risking**

不得因为公司“越来越确定”而追入。

---

# 8. 3× Trigger Rule

原始规则：

> 买入 → 涨 3× → 自动全部卖出

升级为：

# **3× Trigger = Mandatory Re-Underwriting**

达到原始成本 3× 时，不自动卖。

必须重新运行 frozen v5。

---

## Case A — Harvest

如果当前价格重新分析：

```text
HC = NO
Expectation Gap = Neutral / Negative
and/or
3× Burden = HIGH / EXTREME
```

则：

# HARVEST

建议动作：

```text
减仓 50–100%
```

具体比例由：

- Tail Risk
- tax / liquidity
- remaining forward return
- portfolio concentration

决定。

---

## Case B — Continue

如果：

```text
Original thesis worked
+
New evidence created a fresh HC
+
Current-price P3 Positive
+
Current-price 3× Burden LOW / MODERATE
```

则：

# 不因已经赚 3× 而卖。

继续 HOLD / PYRAMID。

---

# 9. Second S-Curve Rule

同一家公司可以有多个 Investment Day-27。

必须重新定义：

```text
Old S-Curve:
Old Bottleneck:
Old Control Point:
Old Expectation Gap:

New S-Curve:
New Bottleneck:
New Control Point:
New Expectation Gap:
```

禁止：

> “因为它以前是 HC，所以现在继续是 HC。”

必须：

> **新的 S-Curve 从当前价格重新独立承保。**

---

# 10. Harvest States

## HARVEST-1 — HC Weakening

如果：

- P1/P2 intact
- P3 从 Strong Positive → Mild Positive
- 3× Burden LOW/MODERATE → HIGH

则：

```text
减至 50–70% Max Position Budget
```

不是 bearish。

只是赔率下降。

---

## HARVEST-2 — Great Company / Priced-In

如果：

- Winner quality 极强
- Control Point 极强
- P3 Neutral / Negative
- 3× Burden HIGH / EXTREME

则：

```text
减至 0–40%
```

取决于用户是否保留 long-term compounder sleeve。

在纯 Day-27 账户中：

> 应更接近退出。

---

## HARVEST-3 — New S-Curve Watch

如果旧 S-Curve 已 priced-in，但新 S-Curve：

- EMERGING / DAY-27 WATCH
- 尚未通过 replication

则：

```text
核心仓位减仓
+
保留 10–30% Max Position Budget
```

用于等待新的 Investment Day-27。

---

# 11. Exit Rules

以下任何一项成立，优先 EXIT / 大幅降低：

## Thesis Kill

- 36m threshold 明显延后
- type-matched replication 失败
- customer economics 恶化
- demand quality structurally deteriorates
- control point 迁移给竞争者
- winner reinforcement 变负
- scale / capital reinforcement 变负
- platform transfer失败

## Investment Kill

- Expectation Gap clearly Negative
- 3× Burden = EXTREME
- market already prices Bull+
- forward risk/reward 不再不对称

## Risk Kill

- refinancing / liquidity cliff
- catastrophic tail risk 概率显著上升
- regulatory / legal event materially changes recoverability
- position concentration 超过外部 risk ceiling 且 forward return 不足以补偿

---

# 12. Position Drift Rule

如果股票上涨导致：

```text
Actual Position
>
Max Position Budget
```

不得仅因为：

> “这是最强 HC”

就无限容忍集中。

必须运行：

# Concentration Re-Underwriting

检查：

```text
Forward P4
Tail Risk
Correlation with portfolio
Liquidity
Drawdown severity
Recoverability
```

默认：

> **公司 thesis 越确定，不代表 portfolio-level idiosyncratic risk 消失。**

---

# 13. Tail-Risk Overlay

v5 已经将 fundamental thesis 与 catastrophic tail risk 分开。

因此：

```text
HC = YES
```

仍可能对应：

```text
Position < 100% Max Budget
```

例如：

- geopolitics
- platform-policy dependency
- binary regulation
- refinancing cliff
- legal liability

输出：

```text
Fundamental HC:
Tail Risk:
Position Cap Adjustment:
Reason:
```

原则：

> Tail Risk 主要调整 position size，而不是偷偷改写产业 thesis。

---

# 14. Monitoring Cadence

本 Skill 不要求机械按天盯盘。

重点追踪 v5 Monitoring Dashboard 里的：

- Technology
- Customer
- Deployment
- Replication
- Economics
- Control Point
- Winner
- Financial
- Consensus
- Valuation

## Mandatory Re-Underwriting Trigger

出现以下任一事件：

1. 财报显著改变 target S-Curve KPI；
2. 新产品跨过 production/commercial threshold；
3. 第二/第三次关键 replication；
4. 新 S-Curve 出现；
5. 竞争者取得 control point；
6. regulatory / legal / geopolitical tail risk变化；
7. market rerating 使 3× burden 跨档；
8. 原始成本达到 3×；
9. Kill Criterion 接近；
10. 公司主动改变 capital allocation / business architecture。

---

# 15. Evidence-First Pyramiding

最优加仓顺序通常是：

```text
Initial HC
        ↓
Position 50–70%

Replication / economics proof
        ↓
70–90%

New key uncertainty eliminated
or
Second Investment Day-27
        ↓
90–100%

Expectation catches up
        ↓
Harvest
```

而不是：

```text
买
↓
跌了补
↓
涨了追
↓
凭情绪决定
```

---

# 16. AppLovin Example

## 2022

v5：

```text
HC = YES
Control Point proof strong
Expectation Gap very positive
3× Burden LOW
```

Execution：

```text
INITIATE
→ 50–70% Max Position Budget
```

## 2023

AXON2：

```text
Model quality
→ ROAS
→ advertiser spend
→ revenue / EBITDA
```

关键 uncertainty 被消灭。

同时 current-price：

```text
HC = YES
3× Burden LOW–MODERATE
```

Execution：

```text
PYRAMID
→ 90–100%
```

即使股价已经明显上涨。

## 2024

```text
Company quality ↑↑
Market recognition ↑↑↑
E-commerce replication incomplete
3× Burden EXTREME
```

Execution：

```text
HARVEST
→ 大幅减仓 / 退出 Day-27 sleeve
```

核心：

> 2023 加仓和 2024 减仓都不是因为价格本身，而是因为 forward underwriting 改变。

---

# 17. Standard Decision Table

| v5 State | Expectation Gap | 3× Burden | Thesis Change | Default Execution |
|---|---|---|---|---|
| TOO EARLY / EMERGING | any | any | insufficient | 0% |
| DAY-27 WATCH | Positive | acceptable | incomplete proof | 0–25% |
| UNDERWRITE | Positive | LOW/MOD | strong but incomplete | 0–25% |
| HC first call | Positive | LOW/MOD | first full proof | 50–70% |
| HC validated | Positive | LOW/MOD | P1/P2 ↑ | 70–90% |
| HC stronger / new Day-27 | Positive | LOW/MOD | major de-risking | 90–100% |
| HC but burden HIGH | Mild Positive | HIGH | quality strong | Hold / Harvest |
| LATE / PRICED-IN | Neutral/Negative | HIGH/EXTREME | thesis intact | Harvest |
| FALSE EXPECTATION RESET | Negative | any | thesis deteriorating | Exit |
| Veto triggered | any | any | broken | Exit |

---

# 18. Mandatory Output Format

每次使用本 Skill 输出：

```text
EXECUTION VERDICT

Company:
Date:
Upstream v5 Classification:
Specific S-Curve:
Current Position:
Max Position Budget:

Thesis Clock:
P1:
P2:
P3:
P4:
Expectation Gap:
3× Burden:
Tail Risk:
Critical Veto:

Position Clock:
Current State:
Target State:
Target Position (% of Max Budget):
Action:
- INITIATE / ADD / HOLD / HARVEST / EXIT

Why Now:
Evidence Added Since Last Underwrite:
Evidence Lost Since Last Underwrite:

De-Risking vs Re-Rating:
- Fundamental De-Risking:
- Market Re-Rating:
- Which is faster:

Current-Price Test:
“If I had zero position today, would I buy at this price?”
YES / NO

3× Trigger Status:
- Not reached
- Reached → Mandatory Re-underwrite
- New Day-27 overrides mechanical exit

Position Risk:
Tail-Risk Cap:
Concentration Check:

Next Add Trigger:
Next Harvest Trigger:
Hard Exit / Kill Criteria:
```

---

# 19. Quick Mode

用户只问：

> “现在应该加仓还是减仓？”

只运行：

1. 当前 v5 classification
2. 上次 vs 本次 P1–P4
3. Expectation Gap
4. 3× Burden
5. new evidence
6. De-Risking vs Re-Rating
7. Tail Risk
8. Current-price zero-position test

输出：

```text
ACTION:
TARGET POSITION:
WHY:
WHAT CHANGED:
NEXT ADD TRIGGER:
NEXT HARVEST/EXIT TRIGGER:
```

---

# 20. Forbidden Execution Patterns

## Cost-Basis Anchoring

> “我成本很低，所以可以继续拿。”

禁止。

---

## Mechanical 3× Exit

> “已经 3×，所以一定卖。”

禁止。

正确：

> 3× → Mandatory Re-underwrite。

---

## Averaging Down Without Evidence

> “跌了 40%，更便宜，多买。”

禁止。

---

## Price-Chasing

> “涨得很强，证明市场认可，多买。”

禁止。

---

## Thesis-Chasing

> “公司越来越好，所以不看估值。”

禁止。

---

## Permanent Winner Assumption

> “以前是 HC，所以以后一直是 HC。”

禁止。

---

## Position-Driven Research

> “仓位很重，所以把 counter-evidence 解释掉。”

禁止。

---

# 21. Highest-Level Mental Model

```text
FROZEN V5
判断产业 / Winner / 赔率
        ↓
第一次 HC
        ↓
建立主要仓位
        ↓
新 evidence
        ↓
重新承保
        ↓
De-risking > Re-rating ?
        ↓
YES → Pyramid
NO  → Hold / Harvest
        ↓
3× reached
        ↓
Mandatory Re-underwrite
        ↓
Current-price forward 3× still HC?
        ↓
YES → Continue / Add
NO  → Harvest / Exit
```

最终原则：

> **买入不是因为股价低，加仓不是因为股价涨，卖出也不是因为赚得多。**

而是：

# **仓位始终服从“当前价格下、当前证据下”的 forward underwriting。**

---

# 22. Relationship to v5

`industry_analysis_skill_v5` 是：

# Research / Underwriting Constitution

本 Skill 是：

# Capital Allocation / Execution Constitution

两者关系：

```text
Frost-Based Industry Evolution Analysis
        ↓
industry_analysis_skill_v5
        ↓
HIGH-CONVICTION / NO
        ↓
industry_analysis_execution_skill_v1
        ↓
ENTER / PYRAMID / HOLD / HARVEST / EXIT
```

本 Skill 不修改 frozen v5。

如果执行层历史 / 实盘出现系统性问题：

> 只升级本 Skill，除非问题明确来自 v5 的研究判断本身。

---
