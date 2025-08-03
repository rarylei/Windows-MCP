<div align="center">
<h1>🪟 Windows-MCP</h1>
<a href="https://github.com/CursorTouch/Windows-MCP/blob/main/LICENSE">
<img src="https://img.shields.io/badge/license-MIT-green" alt="许可证">
</a>
<img src="https://img.shields.io/badge/python-3.13%2B-blue" alt="Python">
<img src="https://img.shields.io/badge/platform-Windows%207–11-blue" alt="平台: Windows 7 到 11">
<img src="https://img.shields.io/github/last-commit/CursorTouch/Windows-MCP" alt="最近提交">
<br>
<a href="https://x.com/CursorTouch">
<img src="https://img.shields.io/badge/follow-%40CursorTouch-1DA1F2?logo=twitter&style=flat" alt="在 Twitter 上关注">
</a>
<a href="https://discord.com/invite/Aue9Yj2VzS">
<img src="https://img.shields.io/badge/Join%20on-Discord-5865F2?logo=discord&logoColor=white&style=flat" alt="在 Discord 上加入我们">
</a>
</div>
<br>
Windows MCP 是一个轻量级的开源项目，旨在实现 AI 代理与 Windows 操作系统的无缝集成。作为 MCP 服务器，它在大型语言模型（LLM）和 Windows 操作系统之间架起了桥梁，使 AI 代理能够执行诸如文件导航、应用程序控制、UI 交互、质量保证测试等任务。
更新
 * 试试 🪟 Windows-Use!!，这是一个基于 Windows-MCP 构建的代理。
 * Windows-MCP 现在已作为桌面扩展程序在 Claude Desktop 中推出。
支持的操作系统
 * Windows 7
 * Windows 8, 8.1
 * Windows 10
 * Windows 11
🎥 演示
https://github.com/user-attachments/assets/d0e7ed1d-6189-4de6-838a-5ef8e1cad54e
https://github.com/user-attachments/assets/d2b372dc-8d00-4d71-9677-4c64f5987485
✨ 主要功能
 * 无缝 Windows 集成
   与 Windows UI 元素进行原生交互，打开应用程序，控制窗口，模拟用户输入等。
 * 支持任何 LLM（视觉可选）
   与许多自动化工具不同，Windows MCP 不依赖于任何传统的计算机视觉技术或特定的微调模型；它适用于任何大型语言模型，从而降低了复杂性和设置时间。
 * 丰富的 UI 自动化工具集
   包含用于基本键盘、鼠标操作以及捕获窗口/UI 状态的工具。
 * 轻量级 & 开源
   依赖项极少，设置简单，提供 MIT 许可下的完整源代码。
 * 可定制和可扩展
   可以轻松调整或扩展工具，以满足您独特的自动化或 AI 集成需求。
 * 实时交互
   动作之间的典型延迟（例如，从一次鼠标点击到下一次）范围为 1.5 至 2.3 秒，并可能因活动应用程序数量、系统负载以及 LLM 的推理速度而略有不同。
前提条件
 * Python 3.13+
 * Anthropic Claude 桌面应用或其他 MCP 客户端
 * 来自 Astra 的 UV（包管理器），通过 pip install uv 安装
 * 来自 Antropic 的 DXT（桌面扩展），通过 npm install -g @anthropic-ai/dxt 安装
 * 将 Windows 的默认语言设置为“英语”
🏁 入门指南
Gemini CLI
 * 在文件资源管理器中导航到 %USERPROFILE%/.gemini 并打开 settings.json。
 * 在 settings.json 中添加 windows-mcp 配置并保存。
<!-- end list -->
{
  "theme": "Default",
  ...
//MCP 服务器配置
  "mcpServers": {
    "windows-mcp": {
      "command": "uv",
      "args": [
        "--directory",
        "<windows-mcp 目录的路径>",
        "run",
        "main.py"
      ]
    }
  }
}

 * 在终端中重新运行 Gemini CLI。享受吧 🥳
Claude Desktop
 * 克隆存储库。
<!-- end list -->
git clone https://github.com/CursorTouch/Windows-MCP.git
cd Windows-MCP

 * 构建桌面扩展 DXT：
<!-- end list -->
npx @anthropic-ai/dxt pack

 * 打开 Claude Desktop：
进入 Claude Desktop：设置 -> 扩展 -> 安装扩展（找到 .dxt 文件）-> 安装
最后，享受吧 🥳。
有关 Claude Desktop 集成故障排除的更多信息，请参阅 MCP 文档。文档中包含检查日志和解决常见问题的有用提示。
🛠️ MCP 工具
Claude 可以使用以下工具与 Windows 进行交互：
 * Click-Tool：在给定坐标处单击屏幕。
 * Type-Tool：在元素上输入文本（可选地清除现有文本）。
 * Clipboard-Tool：使用系统剪贴板进行复制或粘贴。
 * Scroll-Tool：在窗口或特定区域进行垂直或水平滚动。
 * Drag-Tool：从一个点拖动到另一个点。
 * Move-Tool：移动鼠标指针。
 * Shortcut-Tool：按下键盘快捷键（Ctrl+c、Alt+Tab 等）。
 * Key-Tool：按下单个按键。
 * Wait-Tool：暂停一段定义好的时间。
 * State-Tool：结合了默认语言、浏览器、活动应用、交互式、文本和可滚动元素以及桌面截图的快照。
 * Resize-Tool：用于更改应用程序的窗口大小或位置。
 * Launch-Tool：从开始菜单启动应用程序。
 * Shell-Tool：执行 PowerShell 命令。
 * Scrape-Tool：抓取整个网页以获取信息。
Star 历史
⚠️ 注意
该 MCP 直接与您的 Windows 操作系统进行交互以执行操作。请谨慎使用，并避免在无法承受此类风险的环境中部署它。
📝 局限性
 * 无法选择段落中的特定文本部分，因为 MCP 依赖于可访问性树（a11y tree）。（⌛ 正在开发中。）
 * Type-Tool 仅用于输入文本，不适用于在 IDE 中编程，因为它会将整个程序作为一个整体写入文件。（⌛ 正在开发中。）
🪪 许可证
本项目采用 MIT 许可证，详见 LICENSE 文件。
🤝 贡献
欢迎贡献！请参阅 CONTRIBUTING 文件了解设置说明和开发指南。
由 Jeomon George 用 ❤️ 制作
引用
@software{
  author       = {George, Jeomon},
  title        = {Windows-MCP: Lightweight open-source project for integrating LLM agents with Windows},
  year         = {2024},
  publisher    = {GitHub},
  url={https://github.com/CursorTouch/Windows-MCP}
}

