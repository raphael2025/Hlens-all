# Hlens-all

这个仓库整理自我(raphael2025)名下 60+ 个私有/公开项目里沉淀下来的经验:多年加密货币量化研究和交易系统工程里踩过的坑、做过的决策、放弃过的方案。内容经过重写和脱敏,不含账户、密钥、服务器信息,也不含可直接复制的策略参数或实盘业绩数字——目的是分享方法论和教训,不是提供交易建议。

## 目录结构

全部内容在 [`docs/experience/`](docs/experience/) 下,按主题分成 4 类:

### [quant-research/](docs/experience/quant-research/) —— 量化研究方法论(13 篇)

怎么避免回测骗自己、怎么判断一个信号能不能上线。

| 文档 | 内容 |
|---|---|
| [anti-overfitting-methodology](docs/experience/quant-research/anti-overfitting-methodology.md) | 反过拟合检验流程:selection-aware/selection-blind 区别、多重检验的正确记账方式 |
| [backtest-failure-modes](docs/experience/quant-research/backtest-failure-modes.md) | 真实踩过的坑:前视偏差的隐蔽变体、成本与执行侧事故、结构性幻觉 |
| [research-discipline-checklist](docs/experience/quant-research/research-discipline-checklist.md) | 从假设到部署的逐关强制门禁清单 |
| [strategy-findings-map](docs/experience/quant-research/strategy-findings-map.md) | 哪些策略类别被反复证伪、失败机制是什么 |
| [risk-management-principles](docs/experience/quant-research/risk-management-principles.md) | 仓位、回撤与生存:波动率目标化、分数凯利、分层风控 |
| [regime-driven-system-architecture](docs/experience/quant-research/regime-driven-system-architecture.md) | 市场状态驱动的多策略系统架构设计 |
| [research-program-retrospective](docs/experience/quant-research/research-program-retrospective.md) | 组织层面复盘:为什么"做了很多"却"没有进展" |
| [point-in-time-data-contracts-and-leakage](docs/experience/quant-research/point-in-time-data-contracts-and-leakage.md) | 从数据管道角度清点前视偏差,怎么结构性堵死 |
| [preregistration-and-research-governance](docs/experience/quant-research/preregistration-and-research-governance.md) | 预注册与评审闸:实验前先冻结什么、负结果如何归档 |
| [search-objective-design-and-goodhart](docs/experience/quant-research/search-objective-design-and-goodhart.md) | 参数搜索目标函数本身的反预测性,怎么诊断 |
| [from-signal-to-live-deployment-gates](docs/experience/quant-research/from-signal-to-live-deployment-gates.md) | 从"统计显著"到"可以上线"要过哪些关卡 |
| [research-code-review-findings](docs/experience/quant-research/research-code-review-findings.md) | 研究代码 review 的真实发现与检查清单 |
| [market-data-recorder-engineering-gotchas](docs/experience/quant-research/market-data-recorder-engineering-gotchas.md) | 行情采集系统的工程坑:订阅成功不等于有数据 |

### [architecture-evolution/](docs/experience/architecture-evolution/) —— 系统架构演进(5 篇)

一个交易系统项目多次重写背后的决策和放弃的设计。

| 文档 | 内容 |
|---|---|
| [two-product-lineages](docs/experience/architecture-evolution/two-product-lineages.md) | 两条产品线为什么分开、为什么不合并 |
| [persistent-streams-are-not-leased-jobs](docs/experience/architecture-evolution/persistent-streams-are-not-leased-jobs.md) | 一次被放弃的 2.2 万行重写:把长连接建模成租约任务的代价 |
| [codebase-archaeology-before-rewrite](docs/experience/architecture-evolution/codebase-archaeology-before-rewrite.md) | 重写前先做一遍"代码考古"的实践方法 |
| [decisions-with-overturn-conditions](docs/experience/architecture-evolution/decisions-with-overturn-conditions.md) | 带"撤销条件"的决策日志格式 |
| [abandoned-designs-catalog](docs/experience/architecture-evolution/abandoned-designs-catalog.md) | 近 19 项被放弃设计的复盘合集 |

### [trading-execution/](docs/experience/trading-execution/) —— 交易执行系统(5 篇)

怎么搭一套靠谱的交易/模拟执行系统。

| 文档 | 内容 |
|---|---|
| [paper-trading-system-design](docs/experience/trading-execution/paper-trading-system-design.md) | 纸面/模拟交易引擎怎么做到真正可信 |
| [signal-evidence-standards](docs/experience/trading-execution/signal-evidence-standards.md) | 信号有效性证据标准:随机基线、聚类标准误 |
| [multi-timeframe-strategy-lessons](docs/experience/trading-execution/multi-timeframe-strategy-lessons.md) | 一套多时间框架策略从"设计假设"到"证据"的重写过程 |
| [exchange-feed-fidelity](docs/experience/trading-execution/exchange-feed-fidelity.md) | 交易所行情源保真度的实测教训 |
| [multi-agent-coding-workflow](docs/experience/trading-execution/multi-agent-coding-workflow.md) | 多 agent 协作编码的编排设计 |

### [ops-and-monitoring/](docs/experience/ops-and-monitoring/) —— 监控与运维(6 篇)

告警系统怎么设计、运维踩过的坑、一次凭证泄露是怎么发现和补救的。

| 文档 | 内容 |
|---|---|
| [alert-engine-design](docs/experience/ops-and-monitoring/alert-engine-design.md) | 告警引擎设计:去重、升级、防止"狼来了" |
| [monitoring-ops-pitfalls](docs/experience/ops-and-monitoring/monitoring-ops-pitfalls.md) | 44 条真实运维踩坑复盘 |
| [credential-leak-audit](docs/experience/ops-and-monitoring/credential-leak-audit.md) | 一次凭证泄露是怎么被发现、审计、补救的 |
| [design-decision-log](docs/experience/ops-and-monitoring/design-decision-log.md) | 成本/收益导向的设计决策日志方法论 |
| [multi-site-dashboard-design](docs/experience/ops-and-monitoring/multi-site-dashboard-design.md) | 多站点聚合监控看板的通用设计 |
| [production-path-integrity](docs/experience/ops-and-monitoring/production-path-integrity.md) | "测试全绿、功能却是死的"真实案例集 |

## 说明

- 每篇文档末尾都有"来源"行,标注整理自哪个原始项目(仅项目名)。
- 具体策略参数、实盘业绩数字、服务器/账户信息一律脱敏或省略——这里是方法论和教训,不是可以直接抄的东西。
- [docs/experience/README.md](docs/experience/README.md) 有更详细的分类说明和按需求的阅读路径建议。

## 交流

Telegram 群:https://t.me/+E3UdPtwlISVhZDc1
