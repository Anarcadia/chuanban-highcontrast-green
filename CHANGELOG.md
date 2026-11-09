# Changelog / 更新日志

All notable changes to **`chuanban-green`（松绿记事本）** are documented in this file.

---

## [1.0.4] - 2026-11-10

### Added & Changed / 新增与优化
- **Dual-Mode Typography Separation（方案 B：编辑态与阅读态双模式字体职责分离）**:
  - **Reading Mode (`.markdown-rendered`)**: Uses `400 Regular` modern editorial gothic (`vivo Sans` / `OPPO Sans 4.0` / `Sarasa Gothic SC` / `Source Han Sans SC`) for crisp magazine-grade reading, while headings scale to `750 ExtraBold` / `850 Heavy`.
  - **Editing & Source Mode (`.markdown-source-view.mod-cm6`)**: Uses monospace typewriter slab (`Sarasa Mono Slab SC`) with a `3px` deep pine-green active-line ruler bar (`.cm-activeLine`), creating an unmistakable visual shift between drafting and reading.
- **Zero-Install Native OS Dual-CJK Fallback（零预装裸机原厂双黑体自动分流）**:
  - When third-party fonts (`vivo Sans` / `Sarasa Mono Slab SC`) are not installed, Reading Mode and Editing Mode automatically route to distinct built-in OS font families: on macOS, `Hiragino Sans GB` (冬青黑体 W3/W6) for Reading vs `SF Mono / Menlo + PingFang SC / Heiti SC` for Editing; on Windows, `Microsoft YaHei` (微软雅黑) for Reading vs `Cascadia Mono / Consolas + DengXian` (等线) for Editing.
- **Triple Bold Enhancement & Markdown Syntax Stamp Badges（粗体三重强化与 Markdown 语法印章化）**:
  - Fixed Obsidian's default `--font-text-override: "??"` placeholder bypassing `--font-text-theme`.
  - Styled `strong` and `.cm-strong` with `750 ExtraBold` (`vivoSans-Extrabold` / `Sarasa-Mono-Slab-SC-Bold` + `-webkit-text-stroke: 0.2px currentColor`), deep pine-ink text (`#0D2E1D`), sage-green highlight background (`rgba(194, 219, 200, 0.50)`), and a `1.5px` pine-green bottom rule.
  - Styled `.cm-formatting-*` tokens (`**`, `#`, `-`, `>`, `` ` ``) as bordered pine-green monospace stamps and toned down raw `.cm-url` strings to `0.85em` muted monospace.
- **Showcase Screenshot Update（更新 1.0.4 展示主图与推荐字体下载方案说明）**:
  - Updated primary [`screenshot.png`](screenshot.png) (`166.0 KB`) and added recommended font pairing documentation in [`README.md`](README.md).

---

## [1.0.3] - 2026-11-08

### Fixed / 修复
- **Windows / Linux Hidden Frameless `.titlebar` Overlay Fix（修复 Windows/Linux 隐藏标题栏模式下 `.titlebar` 不透明背景遮挡整个顶栏图标）**:
  - Scoped opaque `.titlebar` background & bottom border to `body:not(.is-hidden-frameless) .titlebar`, and explicitly enforced `background: transparent !important; border: none !important; pointer-events: none !important; height: calc(var(--header-height) - 1px) !important` on `body.is-hidden-frameless:not(.starter, .is-popout-modal) .titlebar` while keeping `.titlebar-button-container` interactive.
- **Window Control Safe Space `--frame-left-space` & `--frame-right-space` Preservation（恢复 Windows 右上角 `- □ ×` 窗口按钮与 macOS 红绿灯安全预留区）**:
  - Replaced `padding: 0 !important` / `padding: 0 8px !important` on `.workspace-tab-header-container` with `padding-top: 0 !important; padding-bottom: 0 !important` and explicit `.mod-top-left-space` / `.mod-top-right-space` padding formulas (`calc(8px + var(--frame-right-space, 0px))` on Windows/Linux, `calc(38px + var(--frame-right-space, 0px))` on macOS).
  - Locked `.sidebar-toggle-button` height to `calc(var(--header-height) - 1px) !important` (`35px`) so `position: fixed` secondary toggle buttons in hidden-frameless mode never stretch to `100vh`.
- **Sidebar Icon Inner Padding Reset（消除侧栏小图标内部 `padding: 0 6px` 挤压裁切）**:
  - Reset `.workspace-sidedock / .mod-left-split / .mod-right-split .workspace-tab-header-inner` (`padding: 0 !important; width: 100% !important; height: 100% !important; overflow: visible !important`) so `24×24px` sidebar tab icons center cleanly without clipping.

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
