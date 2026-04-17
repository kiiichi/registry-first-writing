# Structured Writing Template

This folder is a clean reusable template for structured long-form writing with LLMs, especially GPT-5.4.

适用场景：
- doctoral thesis
- journal article
- technical report
- white paper
- grant or fellowship proposal
- other source-heavy, revision-heavy long-form writing

## Core Idea

这套模板不是靠一个万能 prompt 直接写完文档，而是把长文写作拆成五个稳定角色：

- `Master Orchestrator Agent`: 统一入口，只负责路由和拆解任务
- `Shared Registry Agent`: 维护项目控制层
- `Draft Agent`: 在控制层约束下起草或重写
- `Review Agent`: 用稳定 ID 做多轮问题诊断，区分可直接修改和需要作者确认的问题
- `Pre-submission Agent`: 做提交前的格式、语法、缩写、引用和交叉引用完整性检查

同时，把容易漂移的项目真相外置到 `shared/` 中，而不是依赖聊天上下文记忆。
格式示例也放在 `shared/` 之下，但单独进入 `shared/references/`，避免和运行时控制层混在一起。

## Why This Works

这套方法稳定的原因主要有五个：

1. 先路由，再执行。讨论、起草、审查、终审不混在一次回答里。
2. 项目真相外置。claim、术语、结构、图、公式、写作禁忌都写入共享文件，模型不需要反复从历史对话里猜。
3. 控制层和生成层分离。`Shared Registry Agent` 决定“允许怎么写”，`Draft Agent` 只负责“按规则写出来”。
4. 审查层独立。`Review Agent` 不负责自由润色，而是做可追踪的问题账本，这能显著减少越改越乱。
5. 最终提交前再做一次表面合规检查。这样不会把中期的逻辑诊断和末期的格式清理混为一谈。

对 GPT-5.4 来说，这种写法特别有效，因为它把高价值控制信息变成了显式文件，而不是隐式上下文。

## Recommended Startup Order

1. 复制本模板，先不要直接写正文。
2. 与 `Shared Registry Agent` 合作填写 `shared/claim_register.md`、`shared/term_registry.md`、`shared/structure_mapping.md`。
3. 如果项目涉及图或公式，再逐步补 `shared/figure_argument_registry.md` 和 `shared/equation_argument_registry.md`。
4. 把反复出现的坏写法沉淀到 `shared/drafting_constraints.md`。
5. 新线程启动时优先直接使用 `@agents.md`。
6. 只有当项目控制清楚后，再让 `Draft Agent` 起草。
7. 用 `Review Agent` 做多轮修订。
8. 在对外提交、送审、定稿前，再用 `Pre-submission Agent` 做表面合规和引用完整性检查。

## File Map

### `prompts/`

- `Master Orchestrator Agent.md`: 总入口和任务路由
- `Shared Registry Agent.md`: 共享控制文件的维护规则
- `Draft Agent.md`: 受控起草
- `Review Agent.md`: 中期问题诊断与 A/B issue ledger
- `Pre-submission Agent.md`: 提交前格式、语法、缩写与引用完整性检查

### `shared/`

- `claim_register.md`: 项目级 claims、贡献口径、scope 边界
- `term_registry.md`: 术语、缩写、定义边界
- `structure_mapping.md`: 章节或小节功能、内容归属、证据放置
- `figure_argument_registry.md`: 图片放在哪、支撑什么、如何占位
- `equation_argument_registry.md`: 公式放在哪、起什么作用、何时需要读公式正文
- `drafting_constraints.md`: 会跨轮次复发的写作行为问题

### `shared/references/`

- registry 和 constraint 的格式示例与教学示例
- 仅在需要理解 schema、示例粒度、模板写法时按需读取
- 不作为运行时 project truth

## Template Conventions

- `shared/` 直属文件是运行时控制层；`shared/references/` 是示例与格式参考层。
- 所有以 `BASE-` 开头的条目都是模板自带的默认控制项。它们默认生效，不属于占位内容。
- 所有以 `EX-` 开头的条目都应放在 `shared/references/` 中，作为示例，不属于真实项目内容。
- 在 `shared/drafting_constraints.md` 中，`Part I` 是模板默认约束层，`Part II` 是项目约束层；如果两层冲突，以项目约束层为准。
- 活跃的 `shared/*.md` 应尽量只保留默认控制、当前项目真相和少量 `reserved` 骨架，不保留长示例层。
- 可以直接替换示例内容，但尽量保留 schema key、字段顺序和 ID 风格。
- 如果某个文件当前不需要，不要删掉；把条目标成 `reserved` 即可。
- 如果项目写作语言是中文，建议尽早把中文特有的句法约束补进 `shared/drafting_constraints.md`。
- 如果项目几乎不涉及公式或图片，也保留对应 registry，只是保持最小占位结构。

## Minimal Bootstrap Checklist

在开始正文之前，至少回答这几个问题：

- 文档最核心的 2-5 个 claims 是什么？
- 哪些术语必须稳定，不能随意换说法？
- 每一章或每一节各自承担什么功能？
- 哪些图是“论证支撑”，哪些图只是“材料展示”？
- 哪些公式是共享基础，哪些公式只属于局部章节？
- 模型最容易犯的 3-5 个写作错误是什么？

如果这些问题没有明确答案，先补 `shared/`，不要急着大段生成正文。
