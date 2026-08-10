# scope-gate — 任务定级门技能

issue 建票时与实施前的 S/M/L/XL/? 五级分流：升级触发器判级（不看代码量）、三道关卡（建票定级打标签 / 实施前复述交付形态 / 实施中膨胀即拆票）。L 级禁止直接实施。

本仓库是该技能的**单一事实源**，由 skills CLI 治理（与 doc-steward 技能仓库同一惯例）：不进任何业务仓库，改进走本仓库的 commit/PR。

## 安装到本机 agent

```bash
# 直接从 GitHub 安装（--copy 复制为快照；技能更新后重跑同一命令覆盖，skills update 对 --copy 安装不可用）
npx skills add Mang-X/scope-gate-skill --copy

# 或克隆后从本地路径安装
npx skills add <克隆目录路径> --copy
```

## 配套约定

- 消费方 GitHub 仓库需存在 `scope:S/M/L/XL/spike` 五个标签（Nerv-IIP 已建）。
- 实证来源：Nerv-IIP #1512（账本票被单分支一口吃掉，23 commit / 71 文件，事后返工切 6 层）、#1510（六轮审核膨胀）、演示期"开票过急覆盖面太大"复盘。
- 按 writing-skills TDD 流程验证：GREEN 场景下代理守住原 PR 范围、拒绝把「你看着办」解释为扩权授权、按域拆票并准确定级。

## 修改规矩

改技能必须先有失败场景（子代理压力测试暴露的新合理化借口），再改 SKILL.md 堵洞，改完重跑场景验证——与代码 TDD 同一纪律。
