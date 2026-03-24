# 🌈 OpenClaw Dashboard Theme Changer

> Change your OpenClaw Dashboard theme color with one command.

[🇨🇳 中文说明](#中文说明) · [🇺🇸 English](#english)

---

## English

### What is this?

A **skill** (plugin) for [OpenClaw](https://github.com/openclaw/openclaw) that lets you change the Dashboard's accent color in **one sentence**.

### Preview

| Before (default red) | After (custom blue) |
|:---:|:---:|
| 🔴 #ff5c5c | 🔵 #2775b6 |

### Usage

Just tell your OpenClaw assistant:

```
Change my Dashboard to #5865F2
```

Or pick a color by name:

| Color | Hex Code |
|:---:|:---:|
| 🔵 Blue | `#2775b6` |
| 🟣 Purple | `#5865F2` |
| 🟢 Green | `#22c55e` |
| 🟠 Orange | `#f59e0b` |
| 🔵 Cyan | `#14b8a6` |
| 💗 Pink | `#ec4899` |

### How it works

The skill modifies the CSS variables in OpenClaw's built-in Dashboard UI:

```
~/.npm-global/lib/node_modules/openclaw/dist/control-ui/assets/index-9skUWh_g.css
```

It replaces all accent-related red values with your chosen color.

### Installation

The skill is automatically loaded by OpenClaw from:

```
~/.openclaw/workspace/skills/dashboard-theme/SKILL.md
```

Or install via [ClawHub](https://clawhub.com):

```
openclaw skills install openclaw-dashboard-theme
```

### Notes

- ⚠️ Upgrading OpenClaw will **overwrite** the changes — just re-run the command.
- The `danger` / destructive action red (`#ef4444`) is intentionally **preserved**.
- No Gateway restart needed — just **force refresh** your browser (`Ctrl+Shift+R` / `Cmd+Shift+R`).

---

## 中文说明

### 这是什么？

一个面向 [OpenClaw](https://github.com/openclaw/openclaw) 的 **技能（Skill）**，用一句话就能修改 Dashboard 的主题颜色。

### 效果预览

| 修改前（默认红色） | 修改后（自定义蓝色） |
|:---:|:---:|
| 🔴 #ff5c5c | 🔵 #2775b6 |

### 使用方法

直接告诉你的 OpenClaw 助手：

```
把我的 Dashboard 改成 #5865F2
```

或者直接说颜色名：

| 颜色 | 色号 |
|:---:|:---:|
| 🔵 蓝色 | `#2775b6` |
| 🟣 紫色 | `#5865F2` |
| 🟢 绿色 | `#22c55e` |
| 🟠 橙色 | `#f59e0b` |
| 🔵 青色 | `#14b8a6` |
| 💗 粉色 | `#ec4899` |

### 实现原理

技能修改的是 OpenClaw 内置 Dashboard 的 CSS 变量文件：

```
~/.npm-global/lib/node_modules/openclaw/dist/control-ui/assets/index-9skUWh_g.css
```

将所有 accent 相关的红色值替换为你的目标颜色。

### 安装方式

OpenClaw 会自动从以下路径加载技能：

```
~/.openclaw/workspace/skills/dashboard-theme/SKILL.md
```

或通过 [ClawHub](https://clawhub.com) 安装：

```
openclaw skills install openclaw-dashboard-theme
```

### 注意事项

- ⚠️ 升级 OpenClaw 后会**被覆盖**，重新运行命令即可恢复。
- 危险操作按钮的红色（`#ef4444`）会**保留**，不受影响。
- 无需重启 Gateway，只需**强制刷新**浏览器（`Ctrl+Shift+R` / `Cmd+Shift+R`）。

---

## License / 许可证

MIT License — feel free to use, modify, and distribute.
