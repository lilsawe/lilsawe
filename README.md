# 李耀彬 · Li Yaobin

**深圳大学 · 计算机技术 硕士（2027 届）**　|　Java 后端 · AI 应用工程　|　深圳

📧 2352757837@qq.com　|　💬 微信 / 手机：15993696213　|　📍 广东 · 深圳

---

## 👋 关于我

- **深圳大学** 计算机与软件学院 · 计算机技术硕士（2027 届），实验室：**智能服务计算研究中心**（中心主任：张良杰 特聘教授）
- 主攻 **Java 后端**（Spring Boot / MySQL / Redis / 微服务），同时是 **AI 编程工具重度使用者**（Codex / Claude Code），习惯「需求拆解 → AI 生成 → 人工校验」的工程流程
- 做过三段真实工程：华为终端**门店销售助手系统**（含隐私字段加密）、跨境电商 **ERP 服务端**、课程实训 **JavaWeb 商城**
- 科研方向：**机器遗忘与可信 AI**（PyTorch / Transformer / 扩散模型），2 篇论文在投（NeurIPS / ICLR，CCF-A 匿名评审）

## 🛠 技能

| 方向 | 内容 |
|---|---|
| **后端** | Java、Spring Boot、MyBatis-Plus、Spring Cloud / Jalor6 微服务、RESTful API、Maven |
| **数据与中间件** | MySQL（索引 / 事务 / 慢查询优化）、Redis、消息队列、Nginx |
| **AI 工程** | Python、PyTorch、Transformer / 扩散模型；**Codex 等 AI 编程工具重度使用**；LLM 应用与 Agent 工程实践 |
| **工程能力** | Git、Linux、Docker、阿里云 ECS / CDN / OSS、单元测试 |

## 🚀 项目

### 1. [mini-agent](https://github.com/lilsawe/mini-agent) — 从零实现的轻量 AI Agent Runtime

> Python ｜ Agent Runtime ｜ Function Calling ｜ Tracing & Eval

用少量可读代码实现 Agent 的核心工作流，**不是对 LangChain / CrewAI 的封装**，方便快速看清 Agent loop 的真实实现：

- 从零实现 `perceive → think → act → observe` Agent 循环
- 基于 OpenAI-compatible Function Calling 的 LLM 调用封装
- 可扩展工具系统：抽象 `Tool` 基类 + 注册表 + 统一 JSON Schema 描述
- JSONL tracing（记录 LLM request/response、tool_call、tool_result）+ **Evaluation harness**（JSONL 任务集评估工具调用链路，输出 JSON / Markdown 报告）
- 单元测试覆盖工具注册、计算器安全边界、tool-call、tracing 与 eval 流程

```bash
git clone https://github.com/lilsawe/mini-agent && cd mini-agent
pip install -e . && python -m mini_agent
```

### 2. 华为终端 · 门店销售助手系统（企业项目，代码未开源）

- 参与后端服务开发与迭代，支撑门店销售业务的数据查询与维护
- **隐私字段加密**：按字段加密、失败重试、并发控制、分时段低峰执行——在合规约束下完成存量数据治理
- 技术栈：Java / Spring / MySQL / Redis

### 3. 跨境电商 ERP 服务端（企业项目，代码未开源）

- 对接亚马逊 **SP-API**：OAuth 授权、订单与库存同步
- **库存-财务对账**与**补货状态机**：事务 + 幂等设计，防止重复入账
- RBAC 权限体系与接口鉴权；跨境电商 ERP 服务端模块开发

### 4. JavaWeb 商城（课程实训）

- 完成后端模块设计与开发，覆盖商品、订单等核心流程
- 技术栈：Java / Servlet / JSP / MySQL

## 🎓 教育背景

| 时间 | 学校 | 专业 | 说明 |
|---|---|---|---|
| 2024.09 – 至今 | **深圳大学** | 计算机技术 · 硕士（2027 届） | 智能服务计算研究中心；已修 25.5/32 学分，平均绩点 3.25 |
| 2019.09 – 2023.07 | 华北水利水电大学 | 计算机科学与技术 · 本科 | GPA 3.68 / 5.0，专业排名前 10% |

**核心课程**：Java 程序设计、数据库原理及应用、计算机网络、操作系统、数据结构、软件工程、机器学习

## 🔬 科研经历

**深圳大学 · 智能服务计算研究中心**（2024.09 – 至今）

- 方向：机器遗忘与可信 AI；负责模型实现、实验设计与对比评估（PyTorch / Transformer / 扩散模型）
- 2 篇论文在投（NeurIPS / ICLR，CCF-A 类匿名评审），第二作者 + 主要执行人

## 📫 联系我

- 邮箱：**2352757837@qq.com**
- 微信 / 手机：**15993696213**
- GitHub：[@lilsawe](https://github.com/lilsawe)

> 正在寻找 **2027 届校招** 的 Java 后端 / AI 应用工程方向岗位，欢迎联系。

---

<sub>Last updated: 2026-10-05</sub>
