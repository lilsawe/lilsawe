# 李耀彬 · Li Yaobin

**深圳大学 · 计算机技术 硕士（2027 届）**　|　Java 后端 · AI 应用工程　|　深圳

> 两个开源项目：[nanogent](https://github.com/lilsawe/nanogent)（Python · AI Agent Runtime）｜ [order-reliability-kit](https://github.com/lilsawe/order-reliability-kit)（Java · Spring Boot 订单服务实践）

📧 2352757837@qq.com　|　💬 微信 / 手机：15993696213　|　📍 广东 · 深圳

<p align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=lilsawe&show_icons=true&hide_border=true&include_all_commits=true&count_private=true" alt="GitHub Stats" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=lilsawe&layout=compact&hide_border=true&langs_count=6" alt="Top Languages" />
</p>

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

## 📦 开源项目

| 项目 | 说明 | 语言 | 许可 |
|---|---|---|---|
| [**nanogent**](https://github.com/lilsawe/nanogent) | 从零实现的轻量 AI Agent Runtime：Agent loop、Function Calling、工具注册表、JSONL tracing、Eval harness；7 项测试 + CI 全绿 | Python | MIT |
| [**order-reliability-kit**](https://github.com/lilsawe/order-reliability-kit) | 订单可靠性工程实践：接口幂等三层防线、订单状态机、双向对账；Swagger 可直接试接口 + 12 项一键冒烟；**36 项测试**（含 200 线程并发幂等）+ JaCoCo 覆盖率 90% + CI 全绿，附**可复现压测脚本** | **Java 17** | MIT |

> 其余企业项目与在投论文代码因**保密 / 双盲评审**原因暂不公开，可在面试中详细说明设计与实现。

## 🚀 项目

### 1. [nanogent](https://github.com/lilsawe/nanogent) — 从零实现的轻量 AI Agent Runtime

> Python ｜ Agent Runtime ｜ Function Calling ｜ Tracing & Eval ｜ MIT License ｜ GitHub Actions CI

用少量可读代码实现 Agent 的核心工作流，**不是对 LangChain / CrewAI 的封装**，方便快速看清 Agent loop 的真实实现：

- 从零实现 `perceive → think → act → observe` Agent 循环
- 基于 OpenAI-compatible Function Calling 的 LLM 调用封装
- 可扩展工具系统：抽象 `Tool` 基类 + 注册表 + 统一 JSON Schema 描述
- JSONL tracing（记录 LLM request/response、tool_call、tool_result）+ **Evaluation harness**（JSONL 任务集评估工具调用链路，输出 JSON / Markdown 报告）
- **7 项单元测试全绿**，覆盖工具注册、计算器安全边界、tool-call、tracing 与 eval 流程；配 **GitHub Actions CI**（Python 3.11 / 3.12 / 3.13 三版本矩阵）

```bash
git clone https://github.com/lilsawe/nanogent && cd nanogent
pip install -e . && python -m nanogent
```

### 2. [order-reliability-kit](https://github.com/lilsawe/order-reliability-kit) — 订单可靠性工程实践（幂等 / 状态机 / 对账）

> Java 17 ｜ Spring Boot 3.3 ｜ Spring Data JPA ｜ Redis ｜ JUnit 5 ｜ Docker Compose ｜ MIT License ｜ GitHub Actions CI

把后端最容易出事故的三件事做成**可运行、可测试、可复用**的实现——**拆成 kit（可复用库） + example（示例服务）双模块**（Swagger 可直接试接口，12 项冒烟一键验证）：

- **接口幂等三层防线**：Redis SETNX 幂等键（第一层）→ 数据库唯一索引兜底（第二层）→ 重放返回首次创建的订单（第三层）
- **订单状态机**：`CREATED → PAID → SHIPPED / CANCELLED` 集中式流转规则 + @Version 乐观锁防并发覆盖
- **双向对账**：本地订单 vs 渠道结算记录，分类输出「一致 / 本地多 / 渠道多 / 金额不一致」四类结果
- **36 项测试全绿**（kit 15 + example 21），含 **200 线程并发幂等测试**
- **双模块设计**：`kit`（可复用组件：通用状态机 / 双向对账引擎 / 幂等存储自动装配，引入依赖即用）+ `example`（示例服务）
- **真实压测数据**（Apple M4 本机 / 单实例 / H2）：独立幂等键下单 **QPS 2460、P99 229 ms**；**200 并发共用同一幂等键 → 服务端仅 1 笔订单**
- **JaCoCo 覆盖率**：行 85% · 分支 87%；附**可复现压测脚本** `benchmark/load-test.mjs`，CI 上 `mvn verify` 全绿

### 3. 华为终端 · 门店销售助手系统（企业项目，代码未开源）

- 参与后端服务开发与迭代，支撑门店销售业务的数据查询与维护
- **隐私字段加密**：按字段加密、失败重试、并发控制、分时段低峰执行——在合规约束下完成存量数据治理
- 技术栈：Java / Spring / MySQL / Redis

### 4. 跨境电商 ERP 服务端（企业项目，代码未开源）

- 对接亚马逊 **SP-API**：OAuth 授权、订单与库存同步
- **库存-财务对账**与**补货状态机**：事务 + 幂等设计，防止重复入账
- RBAC 权限体系与接口鉴权；跨境电商 ERP 服务端模块开发

### 5. JavaWeb 商城（课程实训）

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
- 🛡 **代码开放策略**：论文评审期间遵守双盲规则不公开代码，**接收后将在本主页开源**（含方法实现、消融实验与评估脚本）

## 📫 联系我

- 邮箱：**2352757837@qq.com**
- 微信 / 手机：**15993696213**
- GitHub：[@lilsawe](https://github.com/lilsawe)

> 正在寻找 **2027 届校招** 的 Java 后端 / AI 应用工程方向岗位，欢迎联系。

---

<sub>Last updated: 2026-10-05</sub>
