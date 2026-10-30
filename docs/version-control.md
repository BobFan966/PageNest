# PageNest 版本管理指南

## 仓库与基线

- GitHub 仓库：<https://github.com/BobFan966/PageNest>
- 远程名称：`origin`。
- 默认分支：`main`，保存已确认的工作。
- 工作分支：`codex/简短任务名`，每项独立修改使用一个分支。
- 规划基线：`planning-baseline-2026-10-30`，保存建立远程版本管理时的资料状态，不是应用发布版本。

保留此前已有的本地提交。当前的文档版本号 `v0.1` 表示首版规划范围，不表示 PageNest 应用已经实现。

## 开始一次修改

先检查是否有未提交内容；若有，先确认归属并保存，避免混入新任务。

```bash
git status
git switch main
git pull --ff-only
git switch -c codex/task-name
```

`task-name` 换成任务名称。`git pull --ff-only` 无法完成时，先检查分歧原因，再决定合并方式，不用强制覆盖解决。

## 保存与同步

提交前检查改动，明确选择需要保存的文件。下面的路径仅作示例，请替换成实际修改的文件。

```bash
git diff
git add README.md docs/version-control.md
git diff --cached
git commit -m "docs: clarify project setup"
git push -u origin HEAD
```

一次提交处理一个清楚的问题。提交说明使用 `docs:`（文档）、`feat:`（功能）、`fix:`（修复）或 `chore:`（维护）等前缀，并说明实际变化。

推送工作分支后，在 GitHub 创建 Pull Request，检查改动和适用验证结果，再合入 `main`。应用实现后补充自动检查；当前资料基线不宣称通过应用测试。分支合并流程目前是协作约定，未配置 GitHub 强制保护规则。

Git 提交只保存在本机；成功推送后才同步到 GitHub。`.gitignore` 只影响未跟踪文件，不能清除已经提交过的敏感内容，提交前仍应检查暂存区。

## 查看与恢复

```bash
git log --oneline --decorate -10
git show planning-baseline-2026-10-30:README.md
git diff planning-baseline-2026-10-30 HEAD -- docs/
```

要查看整个旧版本，可创建一个独立目录，保留当前工作区：

```bash
git worktree add --detach ../PageNest-planning-baseline planning-baseline-2026-10-30
```

要撤销已经共享的某次提交，在工作分支使用 `git revert <提交编号>` 创建反向提交，检查后按正常流程合并。该命令会实际修改文件，执行前先保存当前工作；如果存在冲突，逐项确认后处理。

不改写已经共享的历史，不通过强制推送或硬重置处理日常撤销。Git 只保存纳入跟踪的文件；数据库、上传内容和被忽略的本地配置需要单独备份。

## 正式发布

首版通过开发计划中的验收门槛后，才建立带说明的 `v0.1.0` 标签。此后按 `v主版本.次版本.修订版本` 管理应用发布；标签对应具体提交，发布说明记录功能、验证结果和已知限制。发布标签及 GitHub Release 不等于已经完成生产部署。
