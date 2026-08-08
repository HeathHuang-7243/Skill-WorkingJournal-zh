---
id: infrastructure-as-code
title: 基础设施即代码（Terraform / Bicep）
domain: Working
proficiency: advanced
years: 6
tools: [Terraform, Azure Bicep, Terragrunt, OpenTofu, GitHub Actions, Azure DevOps]
triggers:
  - "用代码配置或管理云基础设施"
  - "编写或评审 Terraform / Bicep 模块"
  - "重构或模块化基础设施代码"
summary: 编写、评审并运维可复用的基础设施即代码，实现安全的多环境云部署。
related: [solution-architecture-design, cloud-security-compliance]
---

# 基础设施即代码（Terraform / Bicep）

> 示例 —— 技术名称（Terraform/Bicep 和编排平台）来自真实配置；不同的地方换成你的技术栈。

## 当前运营模式（代码仓库 + 编排平台）
- 一个 git 仓库存放所有 Terraform 代码，分为两层：
  - **Modules 模块**：为每个关注点定义部署逻辑（`main`、`variables`、`outputs`）。
  - **Templates 模板**：用环境特定输入和部署意图调用模块。
- 编排平台（例如 StackGuardian / Terraform Cloud / Spacelift）是执行层：
  - 团队从它的 UI 操作部署。
  - 它保存并管理运行所需的 Terraform state。
  - 它用治理控制编排 apply/destroy 工作流。

## 我们遵循的部署结构
1. 按云最佳实践引导 **application landing zone**。
2. 在该 landing zone 内部，为 **Terraform state 提供专用存储账号**。
3. 该 landing zone 中随后的部署从该存储账号读写 state。
4. 之后所有模块/模板运行都必须复用同一个 state 位置，以保证连续性和漂移安全。

## 模块与模板的设计规则
- 每个关注点一个模块；避免"厨房水槽"式模块。
- 输入有类型且显式；输出稳定且有文档。
- 模板组合模块；模板不重复模块内部逻辑。
- 环境差异留在模板输入中，而不是分叉的模块里。

## 交付护栏
- apply 前评审 `terraform plan`。
- state 访问保持最小权限；把 state 当敏感数据对待。
- 不要绕开 IaC 流程对生产资源做点击操作。
- 各环境使用同一套模块，只改变输入值。

## 这种模型下的实际踩坑
- 如果 landing zone 的 state 存储缺失/配置错误，所有下游部署都会被阻塞。
- state 位置漂移（错误的 backend 路径/容器/key）会让资源看起来"全新"，触发不安全的 plan。
- 绕过模块契约的模板侧快速修复会产生长期维护债务。