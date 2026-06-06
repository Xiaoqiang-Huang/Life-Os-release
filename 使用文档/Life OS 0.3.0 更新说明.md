# Life OS 0.3.0 更新说明

## 主要改进

- AI 助手可以根据问题检索本地知识库、日记、任务、项目和记忆，把相关内容作为回答上下文。
- 新增项目任务总览：任务可以归属项目，并可用圆环进度查看项目完成情况。
- 支持显式网页链接读取和网页搜索意图，用于回答用户主动提供的网页问题。
- AI 助手支持从 GitHub Markdown 链接安装 Skill，用作回答方法论参考。
- 知识库长列表支持收起和展开，减少内容太长时的浏览压力。
- 夜晚模式、暗色主题和核心页面对比度继续优化，减少白底白字。

## 旧用户如何更新

如果你已经安装过 Life OS，只替换插件代码文件：

1. 关闭 Obsidian，或先关闭当前 Vault。
2. 打开旧插件目录：`.obsidian/plugins/personal-life-system/`。
3. 只替换这些文件和目录：
   - `main.js`
   - `manifest.json`
   - `styles.css`
   - `assets/`
4. 不要删除或覆盖旧目录里的 `data.json`。
5. 重新打开 Obsidian，并确认 Life OS 可以正常进入 `AI 助手`、`任务`、`知识库` 和 `设置`。

`data.json` 保存授权状态、安装 ID、AI 配置、主题和本地设置。正常更新不应该覆盖它。

## 新用户如何安装

可以直接打开交付包里的 `LifeOS-可直接打开Vault`，或把 `personal-life-system` 文件夹放到自己的 Obsidian Vault：

```text
你的Vault/.obsidian/plugins/personal-life-system/
```

然后在 Obsidian 的社区插件设置里启用 Life OS。

## 安全边界

- 更新包不包含 `data.json`。
- 更新包不包含本地授权码、API Key、用户日记、任务、知识库或记忆文件。
- GitHub Skill 只作为 AI 回答上下文，不会自动执行脚本，也不会跳过写回确认。
- 写入日记、知识库、记忆和复盘仍需要用户确认。
