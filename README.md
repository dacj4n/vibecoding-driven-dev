# Vibecoding-Driven Development Skill

> **SDD 告诉 AI "做什么"，DDD 告诉 AI "怎么组织"，BDD 告诉 AI "行为是什么"，TDD 告诉 AI "怎么算对"。**

## 简介

本 Skill 将 TDD、BDD、DDD、SDD 四大方法论融合为一个结构化工作流，让 AI 辅助开发从"氛围驱动"升级为"工程驱动"。无需开发经验，按流程一步步走即可。

## 文件结构

```
vibecoding-driven-dev/
├── SKILL.md                    # 入口 — 核心理念 + AI规则 + 流程索引
├── phase-1-sdd.md              # Phase 1 详细指导：规格驱动
├── phase-2-ddd.md              # Phase 2 详细指导：领域建模
├── phase-3-bdd.md              # Phase 3 详细指导：行为场景
├── phase-4-tdd.md              # Phase 4 详细指导：测试驱动
├── phase-5-implement.md        # Phase 5 详细指导：AI 实现
├── README.md
└── templates/
    ├── sdd-spec-template.md    # SDD 规格文档模板
    ├── ddd-model-template.md   # DDD 领域模型模板
    ├── bdd-feature-template.md # BDD Gherkin 场景模板
    └── tdd-test-template.md    # TDD 测试要点模板
```

## 触发方式

在对话中提及以下关键词即可触发：
- "用 Vibecoding 方式开发 xxx"
- "用 TDD/BDD/DDD 方式开发 xxx"
- "先写规格再开发 xxx"

## 执行流程

```
Phase 1 → Phase 2 → Phase 3 → Phase 4 → Phase 5
SDD 规格   DDD 建模   BDD 场景   TDD 测试   AI 实现
```

SKILL.md 作为轻量入口（~70 行），AI 根据当前 Phase 按需读取对应的 phase-N-xxx.md 文件，节省 token。

## 适用场景

| 场景 | 推荐流程 |
|------|----------|
| 简单功能 | Phase 1 → 4 → 5 |
| 业务模块 | Phase 1 → 3 → 4 → 5 |
| 复杂系统 | Phase 1 → 2 → 3 → 4 → 5 |

## 参考资料

- [Vibe Coding — IBM Think](https://www.ibm.com/think/topics/vibe-coding)
- [VibeTDD](https://vibetdd.dev/)
- [Spec-Driven Development — Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/spec-driven-development-github-spec-kit-greenfield-intro/)
- [Domain-Driven Design — Microsoft Azure](https://learn.microsoft.com/en-us/azure/architecture/microservices/model/tactical-domain-driven-design)
