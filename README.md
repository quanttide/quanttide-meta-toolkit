# 量潮元领域（quanttide-meta-toolkit）

> META 元领域——对各模块的总结和再次抽象，而非被强制依赖的基础。

## 定位

quanttide-meta 是量潮工具库体系中的**独立领域（元领域）**。它把传统工程体系中"所有库都依赖的 BASE/CORE"拆解掉，转而定义一种**归纳模式（Summarize）**：

- 对各个领域模块的**共同模式**进行再次总结和抽象
- 提供标准字段、标准模型（如 Contract、Event）等归纳特征
- 上层可以**模块化地依赖**，但**不被强制依赖**

**与 BASE/CORE 的本质区别**：

| 模式 | 依赖关系 | 故障风险 |
|------|---------|---------|
| BASE/CORE | 所有库强制依赖 | 一旦变更 → 全系统灾难 |
| META（Summarize） | 可选、模块化 | 可独立迭代，不好用可拆除 |

## 为什么这样设计

1. **消除单点故障**：系统不再有"动了就全崩"的基础库
2. **元领域独立迭代**：元规范（统一概念、概念关系、二次抽象）可以快速更新
3. **领域间一致性治理**：当领域之间出现混乱时，用 META 进行治理（统一概念、统一概念之间的关系、二次抽象）
4. **可拆除**：如果 META 不好用可以直接拆掉——BASE/CORE 是拆不掉的

## 核心功能

1. 未来领域增加时的模式沉淀
2. 领域之间一致性出现混乱时的治理工具
3. 向上层提供通用特性（排列组合）

## 结构

```
quanttide-meta-toolkit/
└── packages/
    └── python/          # 发布名 quanttide，v0.2.0
        ├── storage/     # LocalStorage（跨平台本地存储，XDG 规范）
        └── fields/      # 标准字段（IdField/NameField/TitleField 等）
```

## 与相关仓库的关系

- **quanttide-toolkit**：元仓库，挂载各领域 toolkit（领域层）
- **quanttide-index-toolkit**：入口库（继承 base 历史，推翻重写——人和 AI 找库的入口）
- **quanttide-meta-toolkit**：元领域（本仓库）——接管了原 base 库的职能，但以 Summarize 模式存在

## 来源

本仓库由 quanttide-base-toolkit 拆解而来（2026-08-09）。storage/fields 归纳特征迁入，base 历史由 quanttide-index-toolkit 继承。
