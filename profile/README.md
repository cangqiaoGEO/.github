## cangqiaoGEO · OpenGEO 开源组织

**GEO（生成式引擎优化）的开放标准与开源工具层** —— 让任何企业都能「看见、理解、验证」自己在 AI 里的存在。闭源 SaaS 把「看见」卖 399 美元/月，OpenGEO 把「看见」变成公共品。

### 四步看懂 OpenGEO：写事实 → 测 → 做 → 验

```mermaid
flowchart LR
    A["📖 <b>① 写事实</b><br/>把品牌写成一份文档库：<br/>你是谁 · 卖什么 · 有什么证据<br/><br/><i>opengeo-spec 定规范<br/>品牌 bundle 存内容（git）</i>"]
    B["🔍 <b>② 测</b><br/>拿买家真实问题去问各家 AI，<br/>记录提没提你、引用了谁<br/><br/><i>opengeo-platform 自动测<br/>opengeo-skills 人工采集豆包/元宝</i>"]
    C["✍️ <b>③ 做</b><br/>哪里缺席补哪里：只依据事实库<br/>生产内容，官网改成 AI 读得懂<br/><br/><i>platform Studio 流水线<br/>opengeo-agentready 官网清单</i>"]
    D["⚖️ <b>④ 验</b><br/>复测：发布的内容有没有被<br/>AI 真的引用？分数动没动？<br/><br/><i>判决报告自动写回 ① 的文档库</i>"]
    E["🧭 <b>行业公开基准</b><br/>所有测量的匿名聚合<br/><br/><i>opengeo-index</i>"]

    A ==> B ==> C ==> D
    D ==>|"进入下一轮"| A
    B --> E

    classDef law fill:#fdf3e3,stroke:#b98a2f,color:#3b2f13
    classDef measure fill:#e8eef7,stroke:#2c4a6e,color:#16233a
    classDef make fill:#f6e9e6,stroke:#a63c2e,color:#3a1c16
    classDef pub fill:#e9f2ea,stroke:#3d6b4f,color:#1c2f22
    class A law
    class B measure
    class C make
    class D measure
    class E pub
```

一句话：**先量出你在 AI 里的位置，再按事实补内容，然后复测验证——发布不等于生效，只有 AI 在下一轮真实回答里引用了它，才算数。** 判决写回同一份文档库，循环滚动。（架构纪律：知识只在 git 里写，遥测只在数据库里算，判决以 markdown 写回——单向环流，无双向同步。）

| 角色 | 仓库 | 一句话 |
| --- | --- | --- |
| 门户 | [OpenGEO](https://github.com/cangqiaoGEO/OpenGEO) | 初衷、口径宪章、详解教程、治理 |
| 法 | [opengeo-spec](https://github.com/cangqiaoGEO/opengeo-spec) | OKF 事实规范 · [Bundle 目录规范](https://github.com/cangqiaoGEO/opengeo-spec/blob/main/BUNDLE.md) · [指标宪章](https://github.com/cangqiaoGEO/opengeo-spec/blob/main/METRICS.md) · [行业 Playbook](https://github.com/cangqiaoGEO/opengeo-spec/tree/main/playbooks) |
| 器 · 自动化 | [opengeo-platform](https://github.com/cangqiaoGEO/opengeo-platform) | 证据机器：多引擎测评、SoV、引用池、Studio 内容流水线、归因闭环 |
| 器 · Agent | [opengeo-skills](https://github.com/cangqiaoGEO/opengeo-skills) | 七技全量（S1 诊断 → S7 周测）+ 总控 Agent + WorkBuddy 官方实现 |
| 术 | [opengeo-agentready](https://github.com/cangqiaoGEO/opengeo-agentready) | llms.txt / JSON-LD / 官网 AI 可读清单与 S6 建站技能 |
| 道 | [opengeo-index](https://github.com/cangqiaoGEO/opengeo-index) | **OpenGEO Index**：行业 × 城市 × 引擎公开可见度基准 |

**口径宪章**：不承诺排名第一 · 不承诺被所有 AI 推荐 · 不承诺统一见效天数；只承诺诊断分数 · 改进清单 · 复测对比。违背者的 PR 直接关闭。

📖 在线教程：https://cangqiaogeo.github.io/OpenGEO/course/ ｜ 治理与 RFC：[GOVERNANCE.md](https://github.com/cangqiaoGEO/OpenGEO/blob/main/GOVERNANCE.md) ｜ 发起方：杭州仓桥智能科技

> 2026-08-28 重构（v2）：原 L0–L5 六层收敛为「法 / 器 / 术 / 道」四角色；opengeo-audit 与 opengeo-insights 已并入上表各仓（六维口径升格为指标宪章，S1/S2/S7 入 skills，S6 入 agentready，采集器入 platform）。
