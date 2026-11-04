# PageNest

Your pages. Your data. One place.

PageNest 是正在规划的数据收集网站。首版目标是让创建者完成“创建任务 → 接入独立网页 → 收到数据 → 查看和导出”的闭环。

## 当前状态

当前仓库保存需求、开发计划、评审记录、设计规范和 QuickForm 参考源码。PageNest 应用尚未实现，也未完成运行、部署或发布验收；参考源码及设计预览不能视为可上线的 PageNest 产品。

设计与交互决定以当前文档及逐项评审记录为准；方案确认与实际功能验收分别记录。

## 项目资料

| 文件 | 用途 |
| --- | --- |
| [需求说明](docs/requirements-v0.1.md) | 首版范围、产品规则和验收要求 |
| [开发计划](docs/development-plan-v0.1.md) | 分阶段实施及发布门槛 |
| [评审记录](docs/review-v0.1.md) | 决策、问题及验证边界 |
| [设计规范](DESIGN.md) | 已批准的视觉系统 |
| [交互规范](docs/design-interactions-v0.1.md) | 交互方案及待执行的验收要求 |
| [逐页设计预览](docs/page-designs-2026-11-04.md) | 10 页可操作设计原型、截图与本地验证边界 |
| [协作规则](AGENTS.md) | 修改项目时需要遵守的约束 |
| [版本管理指南](docs/version-control.md) | 提交、分支、同步和恢复方法 |

## 目录

```text
docs/                       需求、计划、评审和协作说明
work/source/                第三方 QuickForm 参考源码快照
work/homepage.html          分析时保存的上游网页快照
work/repository-tree.json   分析时保存的上游目录快照
```

`work/source/` 来自 [wstlab/quickform](https://github.com/wstlab/quickform)，保留其 [MIT 许可证及版权声明](work/source/LICENSE)。该目录供分析参考；其中教师版的启动方式、默认配置及功能描述不代表 PageNest 的实现或生产配置。该许可证适用于上游参考内容，不自动代表 PageNest 新增内容的授权选择。

## 版本管理

远程仓库：[BobFan966/PageNest](https://github.com/BobFan966/PageNest)。默认分支为 `main`，后续独立修改使用 `codex/简短任务名` 分支。

初始规划基线标签为 `planning-baseline-2026-10-30`，仅标记本次资料归档，不表示应用已发布。应用版本 `v0.1.0` 留待首版通过验收后再建立。

环境变量、密钥、数据库、上传内容、依赖及本地工具日志不纳入 Git；可共享的环境变量模板使用 `.env.example`，并只填写示例值。
