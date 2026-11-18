# 消息心情 · Message Moods

DeepSeek Harness plugin for adjustable message moods.

## 在 DSH 页面调概率

1. 打开 DSH 左侧栏的 **插件 → 消息心情**，确认插件已启用。
2. 滚到详情页底部的 **包含的组件**，点击带箭头的 **消息心情 ›**（`message-moods` 行）。
3. 拖动滑块或输入百分比，再点 **保存**。前三项相加最多 100%，剩余概率自动分给正常回复。

| 反应 | 默认概率 | 行为 |
| --- | --- | --- |
| 不回复 | 10% | 保留用户消息并跳过回复。 |
| 复读 | 20% | 原样重复用户的话。 |
| 敷衍回复 | 0% | 由模型结合近期对话生成，最多显示 3 个字符，含标点。 |
| 正常回复 | 70% | 由模型照常回复，概率为 100% 减去前三项。 |

## 安装

从 [发布页](https://github.com/1-lemonade/message-moods/releases/latest) 下载 `.tgz` 到任意文件夹，在该文件夹打开终端并运行以下命令。将 `web` 换成你实际使用的 DSH profile。

```powershell
dsh plugin --profile web add ./dsh-message-moods-1.1.1.tgz
```

## 兼容性

| DSH 版本 | 实测范围 |
| --- | --- |
| `0.2.2-rc.3` | Windows 桌面端已验证页面调节和保存。自带 CLI 的隔离 Web profile 已通过安装与四种回复的模拟模型测试。 |
| `0.2.2-rc.4` | 官方 npm `@deepseek-ai/dsh-llm` 与 `rc.3` 宿主依赖搭配，四种回复通过同组测试。Windows 桌面整包待验证。 |
