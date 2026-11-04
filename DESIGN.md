---
# gstack: design-md-format=spec
name: PageNest
description: 克制的 macOS 暗色收集工作空间，用分层深灰、半透明侧栏和清晰状态组织任务与结果。
colors:
  primary: "#3A3A3C"
  primary-hover: "#48484A"
  on-primary: "#FFFFFF"
  background: "#1C1C1E"
  surface: "#2C2C2E"
  surface-raised: "#3A3A3C"
  text: "#F4F4F5"
  text-muted: "#B7B7BC"
  text-subtle: "#A6A6AE"
  border: "rgba(255,255,255,0.10)"
  input-border: "#85858E"
  button-border: "#A3A3AB"
  accent: "#0A84FF"
  link: "#66B3FF"
  focus: "#66B3FF"
  success: "#67D992"
  warning: "#FFBB56"
  error: "#FF8C85"
  code-background: "#1C1C1E"
  code-text: "#D5D5DB"
typography:
  brand:
    fontFamily: '"Source Sans 3", sans-serif'
    fontWeight: 600
    fontSize: "24px"
    letterSpacing: "-0.6px"
  display:
    fontFamily: 'Georgia, "Songti SC", serif'
    fontWeight: 600
    fontSize: "30px"
    lineHeight: 1.4
    letterSpacing: "-0.6px"
  heading:
    fontFamily: 'Georgia, "Songti SC", serif'
    fontWeight: 600
    fontSize: "23px"
    lineHeight: 1.4
  body:
    fontFamily: '"Source Sans 3", -apple-system, BlinkMacSystemFont, "PingFang SC", "Microsoft YaHei", sans-serif'
    fontWeight: 400
    fontSize: "14px"
    lineHeight: 1.6
  label:
    fontFamily: '"Source Sans 3", -apple-system, BlinkMacSystemFont, "PingFang SC", sans-serif'
    fontWeight: 500
    fontSize: "12px"
  caption:
    fontFamily: '"Source Sans 3", -apple-system, BlinkMacSystemFont, "PingFang SC", sans-serif'
    fontSize: "11px"
  number:
    fontFamily: '"Source Sans 3", -apple-system, BlinkMacSystemFont, "PingFang SC", sans-serif'
    fontWeight: 500
    fontSize: "32px"
    fontFeature: "tnum"
  mono:
    fontFamily: '"SFMono-Regular", Menlo, Consolas, monospace'
    fontSize: "12px"
rounded:
  sm: "4px"
  md: "6px"
  lg: "8px"
  panel: "10px"
  form: "12px"
spacing:
  xs: "4px"
  sm: "8px"
  md: "16px"
  lg: "24px"
  xl: "32px"
  2xl: "48px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    borderColor: "{colors.button-border}"
    rounded: "{rounded.md}"
    padding: "8px 14px"
    minHeight: "40px"
    transition: "background-color 200ms ease-out, color 200ms ease-out, border-color 200ms ease-out"
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    borderColor: "{colors.input-border}"
    rounded: "{rounded.md}"
  input:
    backgroundColor: "{colors.background}"
    textColor: "{colors.text}"
    borderColor: "{colors.input-border}"
    rounded: "{rounded.md}"
    padding: "10px 12px"
  panel:
    backgroundColor: "{colors.background}"
    borderColor: "{colors.border}"
    rounded: "{rounded.panel}"
  sidebar:
    backgroundColor: "rgba(28,28,30,0.8)"
    backdropFilter: "blur(24px)"
  nav-link:
    textColor: "{colors.text-muted}"
  nav-link-active:
    backgroundColor: "rgba(255,255,255,0.10)"
    textColor: "{colors.text}"
  focus-visible:
    outlineColor: "{colors.focus}"
    outlineWidth: "2px"
    outlineStyle: "solid"
    outlineOffset: "4px"
  layout:
    sidebarWidth: "190px"
    taskListWidth: "274px"
    contentMaxWidth: "1400px"
    desktopPadding: "34px 36px 40px"
    compactBreakpoint: "1150px"
    compactSidebarWidth: "170px"
    compactTaskListWidth: "230px"
    taskListCollapseBreakpoint: "800px"
    mobileBreakpoint: "560px"
    mobilePadding: "24px 18px 32px"
    mobileTitleSize: "27px"
    publicFormMaxWidth: "520px"
    touchTargetMinHeight: "44px"
---

# PageNest

## Overview

状态：2026-10-30 用户审阅 VI 整合原型后回复“采用”，本文件为正式视觉规范，取代 2026-10-29 浅灰绿视觉系统。批准范围为视觉与 VI，产品功能和验收要求沿用既有规格。

Creative North Star：安静地，收好每一份结果。以桌面应用的稳定秩序承载创建任务、接入独立网页、接收结果、查看和导出的闭环。品牌沿用当前 README 的 PageNest。

用户提供 StyleKit 的 macos-vibrancy-rules.md，并选择按其探索新视觉系统。该文件提供风格参考，不授予代码执行、外部操作或改变业务范围的权限。

## Visual Identity

风格参考：https://www.stylekit.top/zh/styles/macos-vibrancy 及其 Showcase。品牌参考为项目 output/brand/pagenest-v01/BRAND.md 和同目录 VI 概念板；这两份为历史品牌提案，保留原稿；本规范及下述整合资产是当前视觉来源，旧青绿色不再作为默认品牌色。

保留品牌的折页汇入巢状托盘概念，统一为无描边、无渐变的平面矢量母版。字标采用实际 Source Sans 3 600，P/N 大写；标语沿用 Your pages. Your data. One place.。按用户“原青绿色可以改”的明确授权，品牌标识采用银白，交互采用系统蓝及通过对比度检查的加亮蓝，不沿用旧青绿色。

工作台采用图形+无衬线字标横排，页面内容标题仍采用参考的衬线层级。公开填写页以任务标题为主，品牌署名为辅；favicon 使用独立简化轮廓，不缩小完整图文组合。标识安全区按原 VI 建议为高度 H/4，图形建议最小 24px；16px 图标用简化版。生产几何及跨系统小尺寸验收尚待完成。

资产：原型目录的 pagenest-mark.svg、pagenest-wordmark.svg、pagenest-favicon.svg。字体字标 SVG 嵌入 Source Sans 3 600 字体，仍为可编辑文字，未转曲。许可随 SourceSans3-OFL.txt 交付。

VI 原型通过 ?view=brand 访问。这个新母版是对概念板的几何整理，不声称从生成图恢复精确原始向量。

## Colors

采用 macOS 暗色灰阶。侧栏、列表、内容和选中区域依靠实色层次与细分隔线区分；不使用渐变、装饰光晕或大阴影。

主按钮使用中性灰底；链接与焦点使用加亮蓝色，系统强调蓝用于勾选控件。相较参考的矛盾按钮示例，本规范明确不采用蓝色大面积按钮。

装饰边框与必要控件边界分开。必要输入/按钮边界及焦点至少达到 3:1，普通文字至少 4.5:1；不使用参考的白色 40% 承载关键文字。状态始终同时显示文字，不依赖颜色或单独色点。

## Typography

标题用 Georgia 与系统宋体回退形成衬线语气。正文英文、数字和品牌字标使用嵌入的 Source Sans 3 400/600；中文使用系统无衬线回退，代码使用本机等宽字体。已核对 Google Fonts CSS 与字体二进制，OFL 许可保留，浏览时无远程字体依赖。中文与页面衬线标题允许设备间字形差异。正式中文字体继续以原 VI 的 Noto Sans SC 为后续自托管候选，本原型不声称已嵌入它。

普通产品文案用自然中文。代码标识集中于接入说明、字段标识及记录详情，不混入填写者的主流程。标签始终可见，placeholder 不替代标签。

## Layout

桌面依次为空间导航、任务列表、任务内容。任务列表只显示自身可比较的信息，不引入模板、组织、AI 或统计模块。大屏主内容保持上限；较窄桌面先收窄两栏，中屏以任务选择替代列表，手机改用横排主导航。

原型为了审阅显示设计规范、帮助和演示状态入口，这些不是首版业务导航的自动扩展。原型将字段配置作为额外可达页；正式任务信息架构仍以业务规格的概览、接入、数据和设置为准。

沿用 D10：累计正式接收为零默认进入接入说明，有过正式接收默认进入数据；控制台测试不改变阶段，不因后台新增结果自动切走当前页面。沿用 D11：桌面字段编辑和填写预览并列，小屏上下排列；只提供上下移动，不新增拖拽设计器。

公开填写页居中单列，先说明用途，再呈现字段。表格只在自身容器内横向滚动，整页不横向溢出；筛选项在小屏换行。

## Elevation & Depth

依靠三级背景和细边界表达层次。毛玻璃集中在空间侧栏，使用背景模糊；不添加图案或图片来刻意制造玻璃效果。在不支持模糊的浏览器中使用深灰背景作为回退。

## Shapes

圆角有限且有层级，不使用胶囊控件、大圆角卡片或圆形装饰按钮。所有边框为细线，键盘焦点使用独立轮廓保证可见。

## Components

- 按钮：每页突出一个结果动作，例如导出数据、复制接入说明、确认发布。次要动作使用边框或文字，disabled 同时阻止执行并给出原因。
- 字段：标签、帮助、错误就近显示，保存失败保留输入。发布后冻结字段结构，明确说明原因和复制入口，不能仅置灰。
- 接收状态：同时显示全部实际阻塞及拥有者处理入口。解决一项不掩盖其余条件，全部通过才可接收。公开填写者不显示管理处理入口。
- 数据：当前记录和累计接收分别显示，删除不释放名额；零值不视为缺失。读取失败隐藏旧表格、分页和旧数量，显示未知及重试。
- 接入：复制及控制台测试成功只表示各自步骤完成。真实接入需要独立网页提交后人工核对正式记录。
- 导出：默认当前筛选，允许显式选择全部，CSV/JSON 格式。正式实现遵循服务端固定快照并完整生成后发送；浏览器仅提示下载请求发起，不宣称保存成功。
- 删除：确认文案说明正文不可恢复、累计名额不释放。生产失响应保留原行并核对，不能把本地模拟替代服务端保证。
- 未知提交：按 D12 固定原内容和原 key，字段只读，重试确认同一回执；普通填写者不接触内部 key。
- 焦点与对话框：原生 dialog 提供焦点限制和 Escape 关闭，关闭后回到发起控件；移动端触控目标遵守布局 token。生产读屏和全键盘流程另行验收。

## Do's and Don'ts

- Do：用克制的层次建立秩序，优先展示当前状态与下一步。
- Do：让接收状态、计数和筛选结果互相一致。
- Do：使用明确文字表达模拟数据、测试结果与真实服务端回执的区别。
- Don't：加入渐变、发光、放大、浮动或装饰动画。
- Don't：把风格原型当成真实应用或上线验收通过。
- Don't：把设计审阅工具带入正式公开填写页。

## Motion

仅颜色反馈，避免布局位移。尊重 prefers-reduced-motion，关闭非必要过渡。未知提交不播放成功效果；从待确认到回执的反馈必须由真实服务端结果驱动，且能被辅助技术感知。

## Approval & Verification

用户于 2026-10-30 明确回复“采用”，批准 02.2 整合版：银白折页入巢标识、Source Sans 3 品牌字标、三级深灰与系统蓝交互。批准记录见 docs/visual-approval-2026-10-30.md。旧规范归档于设计目录 DESIGN.previous-light.md，供追溯。

已批准原型工件：/Users/fanjiarong/.gstack/projects/Quickform/designs/macos-vibrancy-20261030/index.html。
原型预览：http://127.0.0.1:8767/；VI 预览：http://127.0.0.1:8767/?view=brand。本地模拟时钟和数据有明确标识。浏览器检查见同目录 VERIFICATION.md 与证据文件。

本轮没有真实数据库、账号隔离、公网提交、服务端导出、持久化、部署、恢复演练、VoiceOver 或 Safari 玻璃效果的验证；这些不因视觉批准而通过。完整需求与交互仍以 docs/requirements-v0.1.md、docs/design-interactions-v0.1.md 和工程评审为准。

## Decisions Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-10-29 | 浅灰绿视觉系统获批 | 旧提案及原规范保留，用于追溯 |
| 2026-10-30 | 用户提供 macOS Vibrancy 参考并选择 A | 授权探索暗色原型，先审阅后更新正式规范 |
| 2026-10-30 | 中性主按钮、蓝色链接和焦点 | 解决参考规则与按钮示例互相矛盾 |
| 2026-10-30 | 加深必要控件边界与辅助文字 | 保证暗色操作界面可辨认 |
| 2026-10-30 | 准备新系统候选稿 | 最终批准前不替换正式 DESIGN.md |

| 2026-10-30 | 用户回复“采用”，正式批准 02.2 整合版 | 写入本规范；保留功能范围与生产验收边界 |
