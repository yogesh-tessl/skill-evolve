# 特殊场景

## 快速模式：用户只有一个小问题

如果用户带着一个具体问题来（"这个 skill 生成的格式不对"、"它总是漏掉 X 步骤"），走快速路径：

1. 读 skill → 定位问题段落 → 理解 why
2. 针对性改写（解释给用户听）
3. 建议用户试一下，看看好没好

快速模式适用于：问题明确、改动局部、不涉及 skill 整体架构。如果快速改完用户还不满意，再切到完整循环。

## 用户没有明确的 skill，只有一个模糊的想法

这时候不是 skill-evolve 的场景，而是 skill-creator 的场景。建议用户先用 `/skill-creator` 创建一个初版，再用 `/evolve` 迭代改进。

## skill-evolve 和 skill-creator 的分工

- **skill-creator**：从 0 到 1。用户想要一个新 skill，帮他们写出初版、跑评测、优化触发描述。
- **skill-evolve**：从 1 到 N。用户已有一个能跑的 skill，但质量不满意，需要系统性地观察问题、提炼模式、迭代改进。

两者可以串联：先 `/skill-creator` 出初版，再 `/evolve` 持续打磨。

## 用户带着一个输出来说"这不对"

这是最好的起点。一个真实的失败案例 = 一个免费的测试 prompt。从这个案例开始，补充 2-3 个相关 prompt，直接进入第二步。

## Skill 问题不在指令层，在触发层（description 不准）

如果观察发现 skill 该触发时不触发，或不该触发时触发了，这是 description 的问题。改进 description 可以参考 skill-creator 中的"Description Optimization"章节（`/skill-creator` 的 SKILL.md 中有详细流程）。skill-evolve 聚焦于 skill 被触发后的执行质量。

## 改了 3 轮还不收敛

可能的原因：
1. **skill 职责太宽**——一个 skill 试图覆盖太多场景，应该拆分
2. **测试 prompt 之间矛盾**——不同 prompt 对 skill 的期望互相冲突，需要和用户对齐
3. **底层能力限制**——有些任务超出了当前模型能力，skill 再怎么改也做不到，诚实告知用户
