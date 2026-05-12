---
name: vibecoding-driven-dev
description: AI Vibecoding 工程化开发方法论。融合 SDD（规格驱动）、DDD（领域驱动）、BDD（行为驱动）、TDD（测试驱动）四大方法论，为 AI 辅助编程提供结构化工作流。从"氛围编程"升级为"工程驱动"。
version: 1.2.0
tags: [vibecoding, tdd, bdd, ddd, sdd, ai-coding, methodology]
---

# Vibecoding-Driven Development

> **SDD 告诉 AI "做什么"，DDD 告诉 AI "怎么组织"，BDD 告诉 AI "行为是什么"，TDD 告诉 AI "怎么算对"。**

将四大方法论融合为结构化工作流，让 Vibecoding 从"氛围驱动"升级为"工程驱动"。

## AI 行为指令

当用户提出开发需求时：
1. 展示"执行流程"总览，让用户了解五步流程
2. 根据"适用场景"表判断复杂度，主动建议用户跳过哪些 Phase
3. 从 Phase 1 开始：读取 [phase-1-sdd.md](phase-1-sdd.md) 并引导用户编写规格
4. 每个 Phase 完成后，读取下一个 Phase 文件继续引导
5. **绝不跳过 Phase 1 直接生成代码**——规格是防止烂代码的第一道防线

## 适用场景

| 你的需求 | 执行流程 |
|----------|----------|
| 简单功能 / 脚本 | Phase 1 → 4 → 5 |
| 业务功能模块 | Phase 1 → 3 → 4 → 5 |
| 复杂业务系统 | Phase 1 → 2 → 3 → 4 → 5（完整流程） |

## 🤖 AI 协作核心规则

> 贯穿所有 Phase，每次与 AI 对话都要遵守。

**规则 1：一次只做一件事。** 大任务拆小，每次只让 AI 完成一个。一次扔所有需求 = 收获不可维护的代码。

**规则 2：规格之外不添加。** AI 喜欢主动加功能，每次必须明确约束："只实现规格中的功能，不要过度设计，保持代码简单。"

**规则 3：测试不过不继续。** 测试不通过绝不进入下一个任务。修 3 次还不好 → 拆更小；多次修不好 → 回 Phase 1 检查规格是否清晰。

**规则 4：每阶段有检查，不跳步。** 宁可多花 5 分钟在规格上，也不花 5 小时修 AI 的烂代码。

## 执行流程

```
Phase 1 → Phase 2 → Phase 3 → Phase 4 → Phase 5
SDD 规格   DDD 建模   BDD 场景   TDD 测试   AI 实现
```

**执行方式：** 从 Phase 1 开始，读取对应文件 → 完成产出物 → 通过 ✅ 检查 → 进入下一 Phase。不要跳步。

| Phase | 读取文件 | 核心问题 | 产出物 |
|-------|---------|----------|--------|
| Phase 1: SDD | [phase-1-sdd.md](phase-1-sdd.md) | "做什么" | 规格文档 |
| Phase 2: DDD | [phase-2-ddd.md](phase-2-ddd.md) | "怎么组织" | 领域模型 |
| Phase 3: BDD | [phase-3-bdd.md](phase-3-bdd.md) | "行为是什么" | Gherkin 场景 |
| Phase 4: TDD | [phase-4-tdd.md](phase-4-tdd.md) | "怎么算对" | 测试要点清单 |
| Phase 5: 实现 | [phase-5-implement.md](phase-5-implement.md) | "写出来" | 代码 + 验证 |

## 模板文件

各 Phase 产出需要填空时，参考对应模板：

| 方法论 | 模板 |
|--------|------|
| SDD | [templates/sdd-spec-template.md](templates/sdd-spec-template.md) |
| DDD | [templates/ddd-model-template.md](templates/ddd-model-template.md) |
| BDD | [templates/bdd-feature-template.md](templates/bdd-feature-template.md) |
| TDD | [templates/tdd-test-template.md](templates/tdd-test-template.md) |

## 常见陷阱

| 陷阱 | 正确做法 |
|------|----------|
| 跳过 SDD 直接让 AI 写代码 | 先写规格，哪怕只有 5 行 |
| 一次把所有需求扔给 AI | 每次只给一个任务，逐个击破 |
| 只测正常流程，不测异常 | 至少 30% 的测试覆盖异常和边界 |
| AI 写错了就放弃流程 | 回到 Phase 1 检查规格是否描述清楚了 |
| 代码能跑起来就不管了 | 对照验收标准逐条确认，清除多余功能 |

## 快速开始

> 用户输入："帮我做一个待办事项应用"

1. **Phase 1 — SDD**：FR1 创建待办(标题/优先级/截止日) FR2 高/中/低优先级 FR3 标记完成。AC：创建后立即显示；空标题时提示。
2. **Phase 2 — DDD**：Todo(任务)、Priority(HIGH/MEDIUM/LOW)、TodoList(集合)
3. **Phase 3 — BDD**：Given 用户在页面，When 输入标题选优先级，Then 列表显示。异常：空标题→提示错误。
4. **Phase 4 — TDD**：test_create_success、test_empty_title_error、test_mark_completed
5. **Phase 5 — 实现**：把以上 4 步产出组织成提示词，逐任务让 AI 实现，测试通过再继续。

## 参考资料

- [Vibe Coding — IBM Think](https://www.ibm.com/think/topics/vibe-coding)
- [VibeTDD](https://vibetdd.dev/)
- [Spec-Driven Development — Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/spec-driven-development-github-spec-kit-greenfield-intro/)
- [Domain-Driven Design — Microsoft Azure](https://learn.microsoft.com/en-us/azure/architecture/microservices/model/tactical-domain-driven-design)
