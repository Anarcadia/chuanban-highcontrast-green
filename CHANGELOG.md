# Changelog / 更新日志

All notable changes to **`chuanban-green`（松绿记事本）** are documented in this file.

---

## [1.0.2] - 2026-11-08

### Fixed / 修复
- **Top-Left Ribbon & Sidebar Header `4px` Step Fix（修复左上角窄边栏收起钮与侧栏标签栏 `4px` 断差）**:
  - Locked `--header-height: 36px !important` globally and aligned `.workspace-ribbon`, `.workspace-ribbon::before`, and `.sidebar-toggle-button.mod-left` to `36px` (`border-box`), eliminating the `4px` vertical step caused by Obsidian's native `40px` `--header-height` default.
- **Active Tab `6px` Downward Overflow Fix（修复主工作区绿色激活 Tab 向下溢出 `6px` 压线问题）**:
  - Reset Obsidian's native `.workspace-tab-header-container-inner` offsets (`margin: 5px -6px -1px; padding: 1px 6px 0px`) to `margin: 0; padding: 0; height: 100%`, and locked `.mod-root .workspace-tab-header` to `height: 100%` (`border-box`) so active tabs sit flush above the continuous `1px` bottom grid line (`y = 36px`).
- **Sidebar Icon Button Box Alignment（统一左上角收起钮与侧栏图标按钮尺寸）**:
  - Standardized `.mod-left-split .workspace-tab-header` and `.mod-right-split .workspace-tab-header` icon boxes from `26×26px` to `24×24px` to match `.sidebar-toggle-button .clickable-icon`, ensuring flush horizontal alignment and balanced bottom shadow clearance.

---

## [1.0.1] - 2026-11-08

### Changed / 变更
- **Official Showcase Images（替换官方展示主图并新增视觉图解）**:
  - Updated primary showcase image [`screenshot.png`](screenshot.png) (`134.4 KB`) and added secondary annotated visual breakdown [`screenshot-overview.png`](screenshot-overview.png) (`171.7 KB`) in [`README.md`](README.md).

---

## [1.0.0] - 2026-11-08

### Added / 新增
- **Initial Official Release of `chuanban-green`（松绿记事本首发正式版）**:
  - **Exposed `1px` High-Contrast Grid & `0px` Sharp Corners**: Full Neo-Brutalist Swiss grid across sidebars, tabs, breadcrumbs, tables, and popovers.
  - **3-Tier Warm Newsprint Palette**: `#ECEAE2` (main reading sheet), `#E2DFD5` (sidebars/toolbars), and `#D6D2C6` (outline/deep surface), plus full `.theme-dark` Dark Moss Edition support.
  - **Forest & Sage Green Accents with Hard-Edge Shadows**: `#78AB88` solid active tab blocks, `#26593F` `2px` underline internal links, and `3px 3px 0px #A3C9AE` zero-blur hard shadows.
  - **Mechanical Rectangular Toggles & Sliders**: Integer-pixel rectangular toggle switches and range sliders with `1.5px~2px` micro-chamfers.
  - **Editorial Properties Table & Claudian Deep Integration**: Decoupled button padding, `148px` property label column width, date-picker icon clearance, and full Claudian / Bases / Notebook Navigator / Style Settings compatibility.
