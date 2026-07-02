# extension/

该目录为“可直接加载”的示例扩展目录，用于复现与调试注入流程。

包含内容：

- `manifest.json`：Manifest V3 配置
- `content.js`：内容脚本入口（当前为 no-op，不再实现隐藏浏览器系统级全屏提示）

加载方式：

- Chrome：`chrome://extensions` → 开发者模式 → 加载已解压的扩展程序 → 选择本目录
