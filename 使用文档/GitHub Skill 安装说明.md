# GitHub Skill 安装说明

Life OS 的 AI 助手可以从 GitHub 安装你自己维护的 Markdown Skill。Skill 会作为 AI 回答时的思考视角和方法论补充，不会绕过写回确认，也不会自动改动日记、任务、知识库或记忆。

## 入口

1. 打开 Obsidian 里的 Life OS。
2. 进入 `AI 助手`。
3. 在 `名人 Skill（公开方法论）` 区域点击 `展开选择`。
4. 点击 `安装 GitHub Skill`。
5. 粘贴 GitHub 上的 Markdown 文件链接，先预览，再点击安装。

## 支持的链接

支持 GitHub 上的 Markdown 文件链接，例如：

- `https://github.com/<owner>/<repo>/blob/<branch>/path/SKILL.md`
- `https://raw.githubusercontent.com/<owner>/<repo>/<branch>/path/SKILL.md`

当前只支持 `.md` 或 `.markdown` 文件。插件不会把 GitHub release 安装包、zip 包或插件更新包当成 Skill 安装。

## 安装后保存在哪里

安装成功后，Life OS 会做两件事：

- 把 Skill 的 Markdown 副本保存到当前 Vault 的 `Skills/Imported/<skill-id>.md`。
- 把 Skill 的来源、名称、更新时间和本地路径保存到插件设置中。

如果再次粘贴同一个 GitHub Skill 链接并安装，会覆盖同一个 Skill 记录，相当于手动更新这个 Skill。

## 安全边界

GitHub Skill 只作为 AI 助手的文本上下文使用。Life OS 会过滤 Skill 里和工具执行相关的声明，例如 `allowed-tools`、`Bash`、`Write`、`Edit`、脚本命令、`npm install`、`curl`、`wget` 等。

这意味着：

- Skill 可以影响 AI 的回答风格、分析框架和检查清单。
- Skill 不能自动执行命令。
- Skill 不能自动写文件。
- Skill 不能跳过 Life OS 的写回确认。
- 更新插件代码时仍然不要覆盖用户原有的 `data.json`，以免影响授权、模型配置和本地设置。

## 建议写法

建议把 Skill 写成普通 Markdown，重点描述：

- 适用场景。
- 回答原则。
- 分析步骤。
- 输出格式。
- 禁止事项。

不要把需要执行的代码、私钥、授权码、API Key、个人身份信息或客户资料写进公开 GitHub Skill。
