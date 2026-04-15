# 左侧导航栏规范（SCM UI）

## 1. 结构与尺寸
- 容器：`a-layout-sider`，深色主题（`theme="dark"`）。
- 默认宽度：中文 `245px`，英文 `260px`。
- 宽度范围：最小 `120px`，最大 `400px`，支持鼠标拖拽右侧 `8px` 热区。
- 高度：`min-height: 100vh`；菜单区高 `calc(100vh - 64px)`，可滚动。

## 2. 菜单层级行为
- 顶层菜单采用“同层仅保留一个展开项”策略。
- `openKeys` 根据当前路由 path 自动推导，确保刷新后仍展开正确父级。
- 折叠侧栏时清空展开项；再次展开时按当前路由恢复展开项。

## 3. 选中与交互状态
- 选中项来源：`selectedKeys = [routeName]`，以路由 `name` 精确匹配。
- 选中效果：沿用 Ant Design Vue dark menu 选中态（深底高亮 + 白字），保持强对比可见。
- Hover 效果：沿用 dark menu hover 态，避免自定义覆盖导致状态不一致。
- 当前分组：父级 submenu 保持展开，用户可明确定位当前菜单归属。

## 4. 折叠态行为
- 折叠后仅保留图标，文本隐藏。
- 菜单文本均需支持 `title` 提示，保证折叠态可识别性。
- 长文案使用省略策略（`white-space: nowrap; overflow: hidden; text-overflow: ellipsis;`）。

## 5. Logo 区与触发器
- 顶部 Logo 高度 `64px`，与 Header 节奏一致。
- 折叠触发图标在 Header 左侧，hover 变为 `#1890ff`。
- 侧栏拖拽手柄 hover 背景：`rgba(24, 144, 255, 0.1)`，光标 `col-resize`。

## 6. 复刻落地要点
- 不要重写 `.ant-menu-item-selected` 颜色，优先保留 Ant 默认 dark 态。
- 必须实现“路由驱动选中 + 展开项恢复”，否则用户会失去导航定位感。
- 必须支持折叠、展开、滚动和长文本省略四项基础能力。

