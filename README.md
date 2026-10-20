# native-gui-skills

Agent skill for [native-gui](https://github.com/lb091188/moonbit-native-gui) — MoonBit 跨平台桌面 GUI 框架。教 AI 按同一套紧凑、克制的观感写界面，三端一致。

只在项目 `moon.mod` 引入 `NoahLiu/native-gui` 且要写或改界面时安装；不用这个库的项目不需要它。

## 安装

```sh
# 装到工程内的 .agents/skills/（推荐，随项目走）
npx skills@latest add lb091188/native-gui-skills --skill native-gui-design --copy -y

# 装到用户级 ~/.agents/skills/（所有项目可用）
npx skills@latest add lb091188/native-gui-skills --skill native-gui-design --agent universal -g --copy -y
```

不用 `npx` 时，clone 后把 `.agents/skills/native-gui-design/` 整个目录拷进目标工程的 `.agents/skills/`。

国内网络不稳可走 gitee 镜像（手工拷贝那条路）：

```sh
git clone https://gitee.com/<镜像账号>/native-gui-skills.git
```

## 内容

- `SKILL.md`：何时用、动手前读什么、五条硬规则、交付前自查、已知陷阱。
- `references/baseline.md`：间距刻度、字阶、圆角、配色比例、密度取法。
- `references/mapping.md`：每个基准值落在 `@style` / `@ui` 的哪个参数上，附可直接照抄的片段。

## 版本

基准与片段按 `NoahLiu/native-gui@0.2.0` 核对，每个参数名与枚举成员都经过 `moon check --target native` 编译验证。库接口变化后需同步复核 `mapping.md`。
