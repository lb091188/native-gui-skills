# native-gui-skills

Agent skills for [native-gui](https://github.com/lb091188/moonbit-native-gui) — MoonBit 跨平台桌面 GUI 框架。教 AI 按同一套紧凑、克制的观感写界面，并用 mng 工具链走完建工程、热更开发、无头验证、打包的完整回路，三端一致。

只在项目 `moon.mod` 引入 `NoahLiu/native-gui` 且要写或改界面时安装；不用这个库的项目不需要它。

## 安装

```sh
# 装到工程内的 .agents/skills/（推荐，随项目走）
npx skills@latest add lb091188/native-gui-skills --skill native-gui-design --copy -y
npx skills@latest add lb091188/native-gui-skills --skill native-gui-dev --copy -y

# 装到用户级 ~/.agents/skills/（所有项目可用）
npx skills@latest add lb091188/native-gui-skills --skill native-gui-design --agent universal -g --copy -y
npx skills@latest add lb091188/native-gui-skills --skill native-gui-dev --agent universal -g --copy -y
```

不用 `npx` 时，clone 后把 `.agents/skills/<技能名>/` 整个目录拷进目标工程的 `.agents/skills/`。

## 内容

两个技能分工：**观感怎么写**看 design，**工具链怎么走**看 dev。

- `native-gui-design/`：界面观感基准。
  - `SKILL.md`：何时用、动手前读什么、五条硬规则、交付前自查、布局纪律、已知陷阱。
  - `references/baseline.md`：间距刻度、字阶、圆角、配色比例、密度取法。
  - `references/mapping.md`：每个基准值落在 `@style` / `@ui` 的哪个参数上，附可直接照抄的片段。
  - `references/recipes.md`：常见界面模式配方（工具栏/表单/卡片网格/列表/空状态/整页骨架）。
- `native-gui-dev/`：mng 工具链工作流与代码组织。
  - `SKILL.md`：装 mng、应用初始化（`mng new` 生成物与 `mng.toml`）、代码组织纪律（界面一律 `.mng`、逻辑才是 `.mbt`）、页面组件与状态归属（自定义组件 props、状态三层、编译器红线）、`mng dev` 热更循环（HOT/COLD 契约与生成码纪律）、无头验证闭环（`mng mcp` 三工具 / `mng inspect` / `@uitest` 直调断言）、打包发布、常见卡点。
  - `references/components.md`：内置组件一行速查——10 个家族的用途、状态参数与事件。

## 版本

- design 技能按 `NoahLiu/native-gui@0.3.3` 核对，每个参数名与枚举成员都经过 `moon check --target native` 编译验证。
- dev 技能按 `mng@0.2.12`（mng-schema 1）核对，生成物清单经真跑 `mng new` 验证，命令面逐条对照 `mng -h`，mcp 工具经 stdio JSON-RPC 实连验证。
- 库接口或工具命令面变化后需同步复核两个技能。
