---
name: scm-ui-design-style
description: 基于 SCM UI 仓库沉淀可复用的企业后台视觉与页面结构规范，输出可直接落地的字体、字号、配色、间距、布局骨架与组件规则。用于在新项目中复刻同一产品风格、统一列表页/表单页/弹窗页设计、或做旧页面风格对齐改造。
---

# SCM UI Design Style

## 概览
复刻 SCM UI 的核心方法是先固定设计 token，再按“布局壳 + 搜索区 + 表格区 + 底部操作栏”的页面骨架搭建页面。优先沿用 Ant Design Vue 1.x 组件语义与全局覆盖策略。

## 工作流
1. 读取并确认设计 token：颜色、字号、间距、圆角、阴影。
2. 选择页面骨架模板：后台主框架页、登录页、列表页、抽屉/弹窗编辑页。
3. 先做结构与层级，再补充交互态（hover、disabled、active、loading）。
4. 对照检查清单进行风格验收；不通过项直接修正。

## 必读参考
- 设计 token 与视觉语言：`references/design-tokens.md`
- 页面骨架与组件规则：`references/page-blueprints.md`
- 左侧导航细则：`references/sidebar-navigation.md`
- 迁移执行清单：`references/migration-checklist.md`

## 输出要求
当用户要求“做成 SCM UI 风格”时，输出必须包含：
- 一份可执行 token 表（至少含主色、文本色、背景色、边框色、字号、间距）。
- 一份页面结构说明（含容器层级和关键区域尺寸/留白）。
- 一份组件级落地规则（按钮、表格、表单、Tabs、Drawer/Modal）。
- 如需产代码，优先产可复制的 Less/CSS 变量与页面骨架代码。

## 约束
- 不随意引入新视觉语言（如渐变、大阴影、夸张圆角）。
- 无业务强需求时，主色仅使用 SCM 红系（`#f5222d`）及其语义衍生。
- 页面默认信息密度应偏高，优先保证数据可读性与操作效率。
