---
name: openclaw-dashboard-theme
slug: openclaw-dashboard-theme
version: 1.0.0
description: Change OpenClaw Dashboard accent color with one command. Provide a hex color code (e.g. #2775b6) and the skill modifies the Dashboard CSS variables.
---

# Dashboard Theme Changer Skill

修改 OpenClaw Dashboard 的主题颜色。

## 触发条件
当用户说"修改 Dashboard 颜色"、"换主题色"、"改变 dashboard 颜色"、"改成某个颜色"时调用此技能。

## 输入
- `color`（必填）：目标十六进制颜色，如 `#2775b6`、`#5865F2`

## 颜色速查表（可选）
- 蓝色 → `#2775b6`
- 紫色 → `#5865F2`
- 绿色 → `#22c55e`
- 橙色 → `#f59e0b`
- 青色 → `#14b8a6`
- 粉色 → `#ec4899`

## 操作步骤

### 1. 确定颜色
直接使用用户提供的 hex 色值，格式必须是 `#RRGGBB`。

### 2. 计算 hover 变体
将主色的 RGB 各加减约 20 得到 hover 色：
- 深 hover（light 模式悬停）：主色 RGB 各 - 20
- 浅 hover（dark 模式悬停）：主色 RGB 各 + 20

### 3. 修改 CSS
**CSS 文件路径：**
```
~/.npm-global/lib/node_modules/openclaw/dist/control-ui/assets/index-9skUWh_g.css
```

**执行替换（6条都要替换）：**
```
#ff5c5c → 主色
#dc2626 → 主色
#e5243b → 主色
#c41e30 → 主色
#ff7070 → 浅 hover
#ef4444 → 深 hover
```

用 `sed -i` 命令替换，例如主色为 `#5865F2`：
```bash
CSS=~/.npm-global/lib/node_modules/openclaw/dist/control-ui/assets/index-9skUWh_g.css
sed -i 's/#ff5c5c/#5865F2/g' $CSS
sed -i 's/#dc2626/#5865F2/g' $CSS
sed -i 's/#e5243b/#5865F2/g' $CSS
sed -i 's/#c41e30/#5865F2/g' $CSS
sed -i 's/#ff7070/#7c7ff0/g' $CSS
sed -i 's/#ef4444/#3b3eb8/g' $CSS
```

### 4. 验证
```bash
grep -oE "#[a-fA-F0-9]{6}" CSS路径 | grep -i "ff5c\|ff70\|dc26\|e53e\|e524\|c41e" | sort | uniq -c
```
结果应为 0（或只有 danger 红）。

### 5. 告知用户
"已改为 [颜色]，请**强制刷新**浏览器（Ctrl+Shift+R / Cmd+Shift+R）或清除缓存。OpenClaw 升级后会被覆盖，下次重新运行此技能即可。"

## 示例

**用户：** "帮我把 Dashboard 改成 #5865F2"
**助手：** 执行上述替换操作，然后回复"已改为紫色 #5865F2，强制刷新浏览器即可 🟣"

## 注意
- danger 色（#ef4444）是危险操作按钮色，应该保留不变
- OpenClaw 升级后会被覆盖，需要重新执行
- 不需要重启 Gateway，刷新浏览器即可
