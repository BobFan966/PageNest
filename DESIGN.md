---
# gstack: design-md-format=spec
name: QuickForm
description: 清楚可靠、操作省心的中文数据收集工作台，以浅灰绿底色和深青绿操作建立秩序。
colors:
  primary: "#146653"
  primary-hover: "#0D5142"
  on-primary: "#FFFFFF"
  background: "#F3F6F5"
  surface: "#FFFFFF"
  text: "#1C302D"
  text-muted: "#5E726D"
  border: "#DBE4E0"
  input-border: "#ADBFB7"
  accent: "#146653"
  tint: "#E7F2ED"
  focus: "#329D87"
  success: "#216644"
  warning: "#865711"
  warning-background: "#FFF4DC"
  error: "#B03B35"
  error-background: "#FFF0EE"
  info: "#245F88"
  info-background: "#EAF3FA"
  code-background: "#203831"
  code-text: "#D7EEE4"
typography:
  display:
    fontFamily: "Noto Sans SC, Source Sans 3, sans-serif"
    fontWeight: 600
    fontSize: "30px"
    lineHeight: 1.35
    letterSpacing: "-0.6px"
  heading:
    fontFamily: "Noto Sans SC, Source Sans 3, sans-serif"
    fontWeight: 600
    fontSize: "20px"
    lineHeight: 1.45
  body:
    fontFamily: "Source Sans 3, Noto Sans SC, sans-serif"
    fontWeight: 400
    fontSize: "14px"
    lineHeight: 1.65
  label:
    fontFamily: "Source Sans 3, Noto Sans SC, sans-serif"
    fontWeight: 500
    fontSize: "12px"
  caption:
    fontFamily: "Source Sans 3, Noto Sans SC, sans-serif"
    fontSize: "11px"
  number:
    fontFamily: "Source Sans 3, Noto Sans SC, sans-serif"
    fontWeight: 600
    fontSize: "34px"
    fontFeature: "tnum"
  mono:
    fontFamily: "JetBrains Mono, Noto Sans SC, monospace"
    fontSize: "11px"
    fontFeature: "tnum"
rounded:
  sm: "5px"
  md: "6px"
  lg: "8px"
  badge: "4px"
  full: "9999px"
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
    rounded: "{rounded.md}"
    padding: "9px 15px"
    transition: "background 150ms ease, transform 150ms ease"
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    borderColor: "{colors.border}"
    rounded: "{rounded.md}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    borderColor: "{colors.input-border}"
    rounded: "{rounded.sm}"
    padding: "10px 12px"
  panel:
    backgroundColor: "{colors.surface}"
    borderColor: "{colors.border}"
    rounded: "{rounded.lg}"
  nav-link:
    textColor: "{colors.text-muted}"
  nav-link-active:
    backgroundColor: "{colors.tint}"
    textColor: "{colors.primary}"
  focus-visible:
    outlineColor: "{colors.focus}"
    outlineStyle: "solid"
    outlineWidth: "3px"
    outlineOffset: "4px"
  layout:
    sidebarWidth: "218px"
    contentMaxWidth: "1280px"
    desktopPadding: "38px 40px 60px"
    compactBreakpoint: "1100px"
    compactSidebarWidth: "178px"
    mobileBreakpoint: "760px"
    mobilePadding: "26px 18px"
    mobileTitleSize: "25px"
    touchTargetMinHeight: "44px"
---

# QuickForm

## Overview

**Creative North Star:** 清楚可靠，操作省心；让教师知道下一步做什么、当前能否收到数据，以及结果是否已经确认。

**Product context:** 面向教师和少量受邀用户的中文数据收集网站。首版围绕创建任务、接入独立网页、接收结果、查看和导出。产品与工程范围以 `docs/requirements-v0.1.md`、`docs/development-plan-v0.1.md` 和 `docs/review-v0.1.md` 为准。

**Mode per surface:** 管理工作台、字段配置和数据页为 Operate；接入说明为 Read + Operate；公开填写页为 Operate，重点是填写、校验和回执。

用户于 2026-10-29 确认风格提案 01，依据现有评审制作，无本轮竞品调研或外部设计意见。

- 内容按任务和下一步排列，主操作容易辨认。
- 收集状态明确，测试与正式记录有文字区分。
- 数据表保留密度与可扫读性，填写页保持轻盈。
- 低装饰、有限圆角，主要依靠文字、留白和分隔线组织页面。

## Colors

**Strategy:** Restrained，品牌主色用于主按钮、导航选中、链接及重点操作；中性色承担大部分信息，语义色只表达状态。

**Light or dark:** 默认浅色，适合教师在课堂和办公环境中反复查看。预览中的深色切换是适配探索，未纳入首版产品范围，其候选值不属于本规范的正式 token。

成功、警告、错误和信息提示必须同时有文字。品牌色不自动等同于业务成功；任务“已开启”与“实际可接收”遵循业务接收条件。正文、辅助信息和边界分别使用对应 token；辅助信息不承载唯一的关键操作或错误解释。

## Typography

中文使用 Noto Sans SC（思源黑体），以清晰字形和稳定字重服务于教学与管理信息；Source Sans 3 承担英文品牌、数字和混排中的拉丁字形，形成紧凑的工作台语气。JetBrains Mono 仅用于代码、字段标识和需要精确比对的标识符，普通用户文案保持自然中文。

字体来自 Google Fonts，2026-10-29 已实时获取 CSS 并确认三个字体声明。中文加载常规、中等、半粗和粗体，英文加载常规、半粗和粗体，代码加载常规和中等；采用 `font-display: swap`，避免字体加载阻塞内容。正式实现可自托管同字体并保留许可，中文字体资源应按实际需求分片。

展示标题与正文保持明显层级；数字使用等宽数字特性帮助列对齐。标签始终可见，placeholder 仅作示例。小号辅助文字不用于正文说明或重要错误提示。小屏标题按布局 token 收敛，输入内容不因追求密度而截断。

## Layout

桌面使用左侧工作空间导航与右侧内容区；尺寸和断点见 `components.layout`。中等宽度收窄导航与外边距。小屏改为横排导航，表单和字段编辑/预览上下排列；数据表在自身容器内横向滚动，页面本身不应产生横向溢出。

工作台以任务名称、有效状态、当前记录、累计接收/上限和下一步构成可比较列表。详情保留概览、接入说明、数据和设置区域；预览侧栏的页面清单是设计审阅导航，不是正式产品信息架构。

沿用 D10：累计正式接收为零的任务默认进入接入说明，曾有正式接收的任务默认进入数据；测试不触发阶段切换，当前操作不被自动跳页打断。沿用 D11：桌面字段列表与当前设置同区，填写预览在旁；不新增拖拽设计器。

公开填写页使用居中的单列表单，适配手机，表单之外不混入管理入口。页面先说明收集用途，再显示字段和提交动作。

## Elevation & Depth

主要使用背景、白色表面与细边框表达层次。数据表、字段预览和接入步骤可有完整边界；普通段落无需再包卡片。默认不使用装饰阴影、发光描边、玻璃模糊或背景光晕。

## Shapes

输入、按钮、面板与状态标记采用分级圆角，值见 `rounded`。导航和表格保持直线对齐；字段设置与字段列表可连续连接，不层层嵌套容器。头像可使用完整圆形，不将所有按钮改为胶囊。

## Components

- **按钮：** 每页突出一个主要结果动作，使用“创建收集任务”“复制给 AI 的接入说明”“导出当前筛选”等具体文案。次要操作用边框或文字。hover 使用主题色变化，active 轻微位移；disabled 同时阻止交互并给出状态解释，不能仅改变透明度。
- **焦点：** 交互元素显示统一 focus-visible 描边，不移除键盘焦点。触控设备使用布局 token 中的最小目标高度。读屏、全键盘与触控仍需在正式实现中专项验收。
- **输入：** 标签、帮助和错误就近显示；错误不能只靠颜色。保存或提交失败保留输入。未知提交按 D12 锁定本次内容，只用原内容和原 key 重试确认；普通填写页不展示内部 key。
- **表格：** 名称和下一步主次清楚，列头可辨认，数字对齐。记录详情可展开或进入详情页，避免所有次级操作都弹窗。当前记录与累计接收/上限分别显示，删除不恢复累计名额。
- **接入进度：** 复制说明和控制台测试只表示各自步骤，不能标记独立网页真实接入完成。外部提交需人工核对正式记录。技术地址和字段契约集中在接入区域。
- **反馈：** 未接入、只有测试、筛选无结果、正文已删、读取失败分别解释；读取失败时数量未知，不显示零或把旧数量当新结果。加载状态不伪造完成，导出中或失败不表示文件完整生成。
- **接收状态：** 状态不只使用开关或色点。D13 的“同时显示全部阻塞原因”仍是待确认交互候选，本次视觉批准不改变该决定的状态。

预览的发布确认、导出提示和静态详情用于表达视觉层级，其具体交互仍需完成剩余设计评审；本规范不将示例自动升级为全部业务交互已经批准。

## Do's and Don'ts

- Do：每页主动作与当前阶段一致，按钮命名具体结果。
- Do：同时用文字和颜色表达接收、错误和未知状态。
- Do：保持字段编辑与预览对应，表格能辨认零值和未填写。
- Do：手机表单单列，表格局部滚动，键盘焦点清楚。
- Don't：用测试成功、复制成功代替真实外部接入验收。
- Don't：混淆当前记录、累计名额、人工开关和实际接收能力。
- Don't：引入紫色渐变、装饰光晕、重复图标卡片或虚构统计。
- Don't：把代码标识和实现细节放入普通填写者的主流程。

## Motion

**Approach:** minimal-functional。动态仅辅助控件反馈，不做自动轮播、长时间入场或页面跳动。

控件过渡使用 `button-primary` token。出现使用 ease-out，消失使用 ease-in，移动使用 ease-in-out。尊重 `prefers-reduced-motion`，关闭非必要位移、平滑滚动和过渡。

**The one authored moment:** 提交结果从待确认转为明确回执，反馈就近出现且可被读屏读取；未知状态不播放成功效果、不自动生成新提交。该表现仍需真实服务端结果驱动。

## Approval & Verification

获批视觉工件：[交互预览](http://127.0.0.1:8766/)；本机保存于 `/Users/fanjiarong/.gstack/projects/Quickform/designs/style-20261029/`，其中 `PROPOSAL.md`、`VERIFICATION.md` 和截图保留提案与验证依据。

桌面已目视检查工作台、字段配置和数据页；手机填写页在窄屏检查无整页横向溢出。得分零值、未知后只读与模拟重试回执、读取失败隐藏旧数量与分页均有本地浏览器证据。没有真实后端、数据库或公网提交验证，不代表完整设计评审、代码或上线验收通过。

本次批准范围是风格及设计规范，不包含首版深色模式或其余未决交互。继续实施前仍需完成原评审保留的交互、可访问性及工程验收。

## Decisions Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-10-29 | 确认“清楚可靠，操作省心”与基于现有评审制作预览 | 用户明确选择，优先呈现收集闭环 |
| 2026-10-29 | 采用风格提案 01，建立正式设计规范 | 用户回复 A 批准风格并写入 DESIGN.md、AGENTS.md |
| 2026-10-29 | 保留 D13 与剩余交互评审的待确认状态 | 视觉批准不替代业务交互决定或运行验收 |
