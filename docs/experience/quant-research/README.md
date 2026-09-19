# 量化研究经验文档

这是一组从多年加密量化研究记录中提炼出来的"经验教训"文档。它们的共同立场是：

> **回测的默认判决是过拟合；负面结论和矛盾才是知识库的骨架；"历史验证过"永远带时间戳。**

文档只保留**方法论、机制和失败原因**，不包含具体策略参数、业绩数字、仓位与杠杆配置或任何账户/基础设施信息。

## 目录

| 文档 | 内容 |
|---|---|
| [anti-overfitting-methodology.md](anti-overfitting-methodology.md) | 反过拟合检验流程：每项检验在防什么、selection-aware 与 selection-blind 的区别、多重检验的正确记账方式、特征级与策略级验证的分工 |
| [backtest-failure-modes.md](backtest-failure-modes.md) | 真实踩过的坑：前视偏差的隐蔽变体、成本与执行侧事故、结构性幻觉、口径漂移与复现失败、"加过滤 ≠ 加 edge" |
| [research-discipline-checklist.md](research-discipline-checklist.md) | 从假设到部署的逐关强制门禁清单，含前向观察与部署门禁的设计 |
| [strategy-findings-map.md](strategy-findings-map.md) | 哪些策略类别被多次独立证伪、失败机制是什么；唯一幸存者自带的三条限定 |
| [risk-management-principles.md](risk-management-principles.md) | 仓位、回撤与生存：波动率目标化、分数凯利、回撤不对称、权益路径 vs 收益序列、分层风控 |
| [regime-driven-system-architecture.md](regime-driven-system-architecture.md) | 市场状态驱动的多策略架构：为什么这样分层、每层的设计纪律与已知陷阱、基础设施沉淀 |
| [research-program-retrospective.md](research-program-retrospective.md) | 组织层面的复盘：为什么"做了很多"却"没有进展"，以及对应的硬规则 |
| [point-in-time-data-contracts-and-leakage.md](point-in-time-data-contracts-and-leakage.md) | 从数据与管道角度清点前视偏差：泄漏发生在哪一步、用什么结构性手段堵死、怎么用测试证明堵死了 |
| [preregistration-and-research-governance.md](preregistration-and-research-governance.md) | 预注册与评审闸：跑实验之前先冻结什么、谁有权把结论从"提案"升级为"已验证"、负结果如何归档 |
| [search-objective-design-and-goodhart.md](search-objective-design-and-goodhart.md) | 搜索目标函数本身的反预测性：怎么诊断、根因为什么通常在折的信息量、把约束做成类型而不是配置 |
| [from-signal-to-live-deployment-gates.md](from-signal-to-live-deployment-gates.md) | 从"统计显著"到"可以上线"的闸门：IC 显著≠可交易、随机基线揭示的市场 beta、上线开关与纸面→实盘晋升门 |
| [research-code-review-findings.md](research-code-review-findings.md) | 研究代码 review 的真实发现与检查清单：NaN 填 0 偏差、文档与实现漂移、性能 bug 如何限制研究纪律 |
| [market-data-recorder-engineering-gotchas.md](market-data-recorder-engineering-gotchas.md) | 行情采集侧的工程坑：订阅成功≠会推数据、完整性分级、历史墙与不可逆采集决策、主机时钟阶跃 |

## 建议阅读顺序

- **想避免自己的回测骗自己**：先读 `anti-overfitting-methodology` → `backtest-failure-modes` → `point-in-time-data-contracts-and-leakage`。
- **要落地一套流程**：读 `research-discipline-checklist` 和 `preregistration-and-research-governance`，配合 `regime-driven-system-architecture`。
- **想知道什么方向不值得再试**：读 `strategy-findings-map`。
- **已经有策略、准备上仓位**：读 `risk-management-principles`。
- **感觉研究在原地打转**：读 `research-program-retrospective`。
- **参数/规则搜索总在样本外崩掉**：读 `search-objective-design-and-goodhart`。
- **信号跑通了、不确定能否上线**：读 `from-signal-to-live-deployment-gates`。
- **要 review 一份研究代码库**：读 `research-code-review-findings`。
- **在搭行情采集/记录系统**：读 `market-data-recorder-engineering-gotchas`。

## 免责声明

以上全部内容是研究记录的经验总结，**不构成任何投资建议**。文中提到的"验证通过"仅指在历史数据上通过了一套特定的统计检验，不意味着未来有效。

---

**来源**：整理自 `quant-system-core-logic`、`trading-strategy-encyclopedia`、`experiment-encyclopedia`、`experience`、`raphael-quant-knowledge-base`、`wiki` 等自有仓库；另有部分文档整理自 `alpha-autogen`、`crypto-paper-research`、`crypto-hybrid-trainer`、`sol-alpha-research`、`Axiom`、`alpha` 等自有仓库（见各文档末尾的来源行）。
