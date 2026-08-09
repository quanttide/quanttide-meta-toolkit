# 量潮元工程库（quanttide-meta-toolkit）

> 归纳的特征，不是各个应用必须遵循的基础。

## 定位

quanttide-meta 是量潮工具库体系的**元工程层**：从各系统归纳出可复用的特征（如 LocalStorage、标准字段），供跨系统保持一致性，并可在新系统里最大限度借用现有规范。所有特征都是**可拆解**的，不强制依赖。

## 结构

```
quanttide-meta-toolkit/
└── packages/
    └── python/          # 发布名 quanttide，v0.2.0
        ├── storage/     # LocalStorage（跨平台本地存储，XDG 规范）
        └── fields/      # 标准字段（IdField/NameField/TitleField 等）
```

## 与 quanttide-toolkit 的关系

- **quanttide-toolkit**：元仓库，挂载各领域 toolkit（领域层）
- **quanttide-meta-toolkit**：元工程库，归纳特征（本仓库）
- **quanttide（发布名）**：未来统一 endpoint 入口，quanttide-* 作为可选插件

## 来源

本仓库由 quanttide-base-toolkit 拆解而来（2026-08-09）。storage/fields 归纳特征迁入，base 退役。
