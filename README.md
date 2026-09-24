# 商业数据分析师

面向增长、转化、留存、收入与经营决策场景的分析方法和轻量意图路由工具。

本项目帮助分析者把业务问题整理成可执行的分析路径：先定义问题与指标口径，再检查数据质量、拆解变化原因，最后提出建议和验证指标。项目提供方法框架、参考资料与关键词路由；实际分析所需的数据和工具由运行环境提供。

## 能力概览

- **结构化分析**：统一问题范围和指标定义，识别数据质量风险，拆解核心业务驱动因素。
- **场景路由**：识别增长、漏斗、留存、收入利润、运营效率、经营诊断和市场调研等请求。
- **专题参考**：提供指标拆解、分析案例、商业报告、市场研究及路由实现说明。
- **行动建议**：将诊断结果连接到建议、优先级和验证指标，帮助形成可跟踪的后续动作。
- **端到端决策框架**：提供“制、称、权、分、备、胜、行、验”现代转译，串联问题定义、资源配置、执行与效果验证。
- **常用分析模型**：涵盖差异桥接、单位经济、情景与敏感性、帕累托与集中度分析，并说明适用边界。

## 快速开始

### 在宿主环境中使用

阅读 [SKILL.md](SKILL.md)，并根据需要参考 `references/` 中的专题材料。宿主需要按自身能力提供业务数据、计算环境或外部搜索工具。

### 在 Node.js 中调用意图路由

项目要求 Node.js 18 或更高版本。路由模块只根据输入文本识别业务分析场景，不访问数据源，也不执行分析。

```js
const { routeSkillIntent } = require("./src");

const result = routeSkillIntent("最近续费率下降，帮我定位原因并给动作建议");
console.log(result.intent); // retention_analysis
console.log(result.promptHint); // 优先做 cohort、续费和流失阶段拆解。
```

也可以传入包含 `message` 字段的对象：

```js
const result = routeSkillIntent({ message: "请分析注册到支付的转化漏斗" });
```

## 支持的分析场景

| 场景 | 路由标识 | 常见问题 |
| --- | --- | --- |
| 增长分析 | `growth_analysis` | 新增、活跃或销售增长变化 |
| 漏斗分析 | `funnel_analysis` | 注册、激活、下单或支付转化 |
| 留存分析 | `retention_analysis` | 留存、复购、续费或流失 |
| 收入利润分析 | `revenue_analysis` | 收入、客单价、毛利或利润结构 |
| 运营效率分析 | `efficiency_analysis` | 人效、库存、履约或资源利用率 |
| 经营诊断 | `business_diagnosis` | 经营波动、异常定位与复盘 |
| 市场调研 | `market_research` | 市场规模、行业趋势或竞争格局 |

## 项目结构

```text
.
├── SKILL.md                     # 核心工作方法与分析规范
├── src/                         # Node.js 意图路由模块
├── test/                        # 路由测试
├── references/
│   ├── business-reporting.md     # 商业报告结构与交付检查
│   ├── examples.md               # 分析案例
│   ├── market-research.md        # 市场研究方法
│   ├── metric-playbook.md        # 指标口径与拆解方法
│   ├── wei-liaozi-business-framework.md # 尉缭子商业分析框架（现代转译）
│   └── router-design.md          # 路由规则与接口说明
├── agents/                       # Agent 元数据
└── CHANGELOG.md                  # 版本变更记录
```

## 边界与依赖

本项目提供分析指导和基于关键词的意图识别，不连接业务数据源、不运行 SQL、不执行统计计算，也不自行进行网页搜索。分析结论依赖宿主提供的数据与计算能力；市场调研依赖宿主提供的搜索工具。路由置信度是启发式分数，不是经校准的概率。

## 本地检查

```bash
npm test
npm run lint
```

## 版本记录

当前版本：**1.6.0**。详细变更见 [CHANGELOG.md](CHANGELOG.md)。
