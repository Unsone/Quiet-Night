# Quiet Night · 静夜

一款适合中文笔记与长文阅读的 Obsidian 主题。深色模式采用接近黑色的深蓝，浅色模式采用接近白色的暖米色，以彩色标题、天蓝色加粗文字和紫色链接区分内容层次。

*A dark navy and warm light theme for Obsidian, with colorful headings, sky-blue bold text, purple links, and expressive task icons.*

灵感与部分样式来自 [Tokyo Night](https://github.com/tcmmichaelb139/obsidian-tokyonight)。无需构建，也无需安装插件即可使用；可选搭配 [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) 调整阅读体验。

## 特性

- **深浅双模式**：近黑深蓝的夜间界面与暖白米色的日间界面。
- **清晰的文字层次**：H1–H5 分别使用红、金黄、绿、蓝、紫，H6 与顶部文件标题随背景切换为白色或黑色。
- **醒目的重点与链接**：加粗文字使用天蓝色，内部链接与 Markdown 链接使用 TokyoNight 紫色。
- **适合中英文混排**：默认正文行高为 1.8，阅读栏宽为 760 px，提供系统中文字体回退。
- **代码配色**：行内代码与围栏代码使用 TokyoNight 色调，和标题配色独立。
- **任务状态图标**：用进度、星标、日程、书签、想法等图标区分任务含义。
- **简洁的文件导航**：选中文件左侧显示 2 px 直竖条。
- **可选个性化设置**：调整正文宽度、行高、圆角、链接颜色与文件列表密度，或启用宋体阅读模式。

## 安装

### 手动安装

1. 从本仓库下载 `theme.css` 和 `manifest.json`。也可以选择 GitHub 的 **Code → Download ZIP**，解压后取出这两个文件。
2. 在 Obsidian 仓库的配置目录下创建 `themes/Quiet Night/`，将两个文件放入其中：

   ```text
   你的 Obsidian 仓库/
   └─ .obsidian/
      └─ themes/
         └─ Quiet Night/
            ├─ manifest.json
            └─ theme.css
   ```

3. 重启 Obsidian，在 **设置 → 外观 → 主题** 中选择 **Quiet Night**。
4. 在外观设置中切换深色、浅色或跟随系统。

如果仓库使用了自定义配置目录，请将 `.obsidian` 替换为实际目录。主题文件夹名称需要与 `manifest.json` 中的 `name` 一致，均为 `Quiet Night`。

### 更新与卸载

更新时，用新版文件替换 `theme.css` 和 `manifest.json`。若界面没有刷新，切换到默认主题后再切回来，或重启 Obsidian。

卸载时，先切换到其他主题，再删除 `Quiet Night` 文件夹。建议将个人调整放在 CSS 代码片段中，以便更新主题时保留。

## 个性化设置

### 使用 Style Settings

安装并启用社区插件 [Style Settings](https://github.com/mgmeyers/obsidian-style-settings)，在插件设置中找到 **Quiet Night · 静夜**。

| 设置 | 默认值 | 说明 |
| --- | --- | --- |
| 正文宽度 | 760 px | 调整阅读栏宽；需开启编辑器设置中的「缩减栏宽」 |
| 正文行高 | 1.8 | 调整正文疏密 |
| 内容圆角 | 10 px | 调整提示框、图片等元素的圆角 |
| 链接颜色 | TokyoNight 紫色 | 深浅模式分别设置 |
| 使用单色标题 | 关闭 | 启用后，各级标题使用正文颜色 |
| 紧凑文件列表 | 关闭 | 减小侧栏条目间距 |
| 宋体阅读模式 | 关闭 | 使用系统中可用的宋体类字体 |
| 使用普通任务复选框 | 关闭 | 启用后关闭特殊任务图标 |

界面强调色、正文字体、界面字体和等宽字体也可以在 Obsidian 的 **设置 → 外观** 中调整。

### 使用 CSS 代码片段

想自定义标题或加粗颜色，可以创建 `.obsidian/snippets/quiet-night-custom.css`，然后在 **设置 → 外观 → CSS 代码片段** 中刷新并启用它。

以下为可直接修改的示例，颜色对应当前默认值：

```css
/* 深色模式 */
body.theme-dark {
  --qn-heading-1: #e3666b;
  --qn-heading-2: #e9c582;
  --qn-heading-3: #84e597;
  --qn-heading-4: #5e93ef;
  --qn-heading-5: #ab71e6;
  --qn-bold: #7dcfff;
  --qn-note-link: #bb9af7;
}

/* 浅色模式 */
body.theme-light {
  --qn-heading-1: #d7646c;
  --qn-heading-2: #bd8d28;
  --qn-heading-3: #3da668;
  --qn-heading-4: #467bd0;
  --qn-heading-5: #a06bc3;
  --qn-bold: #268bbd;
  --qn-note-link: #5a4a78;
}

/* 两种模式通用 */
body {
  --qn-reading-width: 800px;
  --qn-leading: 1.85;
}
```

只保留需要修改的变量即可。`--qn-heading-1` 至 `--qn-heading-5` 对应 H1–H5；`--qn-inverse` 控制 H6 和顶部文件标题；`--qn-bold` 控制加粗颜色；`--qn-note-link` 控制链接颜色。

如果启用了「使用单色标题」，请先关闭该选项再调整各级标题颜色。同一个选项尽量只在 Style Settings 或 CSS 代码片段中的一处配置，避免相互覆盖。

## 任务状态

在笔记中输入以下标记，即可在阅读视图或实时预览中看到对应样式：

```markdown
- [ ] to-do · 待办
- [/] incomplete · 进行中
- [x] done · 已完成
- [-] canceled · 已取消
- [>] forwarded · 已转发
- [<] scheduling · 日程
- [?] question · 疑问
- [!] important · 重要
- [*] star · 星标
- ["] quote · 引用
- [l] location · 位置
- [b] bookmark · 书签
- [i] information · 信息
- [S] savings · 储蓄
- [I] idea · 想法
- [p] pros · 赞成
- [c] cons · 反对
- [u] up · 上升
- [d] down · 下降
```

标记区分大小写，例如 `i` 是信息，`I` 是想法。星标直接写成 `[*]`，不需要反斜杠。纯源码模式主要显示 Markdown 文本。

这些样式用于呈现状态，不提供任务状态循环或日程管理功能。与第三方任务插件搭配使用时，显示效果取决于插件的标记及样式规则。

将 [主题试用笔记](主题试用笔记.md) 复制到仓库的普通笔记目录，即可集中查看标题、引用、提示框、代码、表格和任务图标。

## 字体与代码

主题不包含字体文件，也不会从网络下载字体。字体按系统可用情况回退：

- 正文与界面：Inter → Segoe UI → PingFang SC → Microsoft YaHei → 系统无衬线字体。
- 代码：JetBrains Mono → Cascadia Code → Consolas → 系统等宽字体。
- 宋体阅读模式：Noto Serif SC → Source Han Serif SC → Songti SC → SimSun → Georgia → 系统衬线字体。

缺少某个字体不影响主题使用。在 Obsidian 外观设置中手动指定的字体优先。

围栏代码块需要在起始三反引号后标注语言，如 `javascript`，才能得到对应语法高亮。普通行内代码不进行语言语法分析。编辑与阅读视图使用不同的高亮库，细节可能有所不同。

## 兼容性与反馈

`manifest.json` 声明的最低 Obsidian 版本为 **1.6.0**。这是兼容目标，目前尚未完成覆盖不同 Obsidian 版本、桌面系统及移动端的完整验证。主题包含移动端间距适配，但仍欢迎实际使用反馈。

如果遇到显示问题，请在本仓库的 **Issues** 中提供：

- Obsidian 版本、操作系统，以及深色或浅色模式。
- 问题出现于阅读视图、实时预览还是源码模式。
- 可复现的最小 Markdown 示例，以及不含私人信息的截图。
- 是否启用了 Style Settings、其他 CSS 代码片段或相关插件。

排查样式冲突时，可以临时关闭其他 CSS 代码片段及相关插件，再确认问题是否仍然出现。

## 致谢与许可

- [Tokyo Night for Obsidian](https://github.com/tcmmichaelb139/obsidian-tokyonight)：主题设计灵感、任务图标及代码配色参考。
- [Obsidian Border](https://github.com/Akifyss/obsidian-border)：TokyoNight 所引用的任务图标样式原始来源。
- [Style Settings](https://github.com/mgmeyers/obsidian-style-settings)：提供可选的主题设置界面。

本项目采用 [MIT License](LICENSE)。移植的第三方样式及图标归原作者所有，相关版权声明与许可证保留在 [第三方声明](THIRD-PARTY-NOTICES.md) 和 [licenses](licenses/) 目录中。
