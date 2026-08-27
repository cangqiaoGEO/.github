## cangqiaoGEO · OpenGEO 开源组织

**GEO（生成式引擎优化）的开放标准与开源工具层** —— 让任何企业都能「看见、理解、验证」自己在 AI 里的存在。闭源 SaaS 把「看见」卖 399 美元/月，OpenGEO 把「看见」变成公共品。

### 一套架构：法只写一遍，两个 runtime，一个遥测库

```mermaid
flowchart TB
    subgraph LAW["📜 法 · 唯一书写真相（git markdown）"]
        SPEC["<b>opengeo-spec</b><br/>OKF 规范 · 指标宪章 · 行业 Playbook"]
        BUNDLE["<b>品牌 bundle</b>（每客户一个私有仓）<br/>事实库 · 意图词 · 内容 · 报告"]
    end

    PLATFORM["⚙️ <b>器A · opengeo-platform</b><br/>自动化证据机器<br/>多引擎测评 · SoV · 引用池 · 归因闭环"]
    SKILLS["🤝 <b>器B · opengeo-skills</b><br/>Agent 人机 runtime（WorkBuddy / Claude Code）<br/>无 API 引擎采集 · 创作 · IM 审批"]
    READY["🛠️ <b>术 · opengeo-agentready</b><br/>llms.txt · JSON-LD · 官网 AI 可读清单"]
    INDEX["🧭 <b>道 · opengeo-index</b><br/>行业 × 城市 × 引擎 公开可见度基准"]

    SPEC -. 同一份口径 .-> PLATFORM
    SPEC -. 同一份口径 .-> SKILLS
    BUNDLE ==>|"① git 写入 → 导入"| PLATFORM
    BUNDLE -->|"项目 = 文件夹"| SKILLS
    SKILLS -->|"② 采集/内容回流"| BUNDLE
    PLATFORM ==>|"③ 判决/报告写回 markdown"| BUNDLE
    PLATFORM -->|"匿名聚合"| INDEX
    READY -->|"站点整改清单"| BUNDLE

    classDef law fill:#fdf3e3,stroke:#b98a2f,color:#3b2f13
    classDef qi fill:#e8eef7,stroke:#2c4a6e,color:#16233a
    classDef pub fill:#e9f2ea,stroke:#3d6b4f,color:#1c2f22
    class SPEC,BUNDLE law
    class PLATFORM,SKILLS qi
    class READY,INDEX pub
```

**单向环流**：① 知识只在 git 里写 → ② platform 导入计算（遥测只在数据库里算）→ ③ 判决以 markdown 写回 bundle。每个存储只对自己的领域有写权——没有双向同步，因此没有冲突。

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
