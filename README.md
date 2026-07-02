# Bilibili Fullscreen Tips Blocker（结论与说明）

本仓库最初尝试通过浏览器扩展拦截 Bilibili 在全屏时出现的退出提示。但在 Edge/Chromium 环境中，用户常见的“bilibili.com — 要退出全屏，请按 esc”提示属于浏览器系统级全屏 UI（安全提示），不属于网页 DOM，无法被内容脚本或油猴脚本隐藏。

因此，本项目当前定位为“结论/说明文档项目”：记录排查过程、原因与可替代方案，避免读者在同一路径上重复投入。

## 结论

- Edge/Chromium 的系统级全屏提示属于浏览器 UI，不在网页 DOM 内
- 扩展的 content script 只能操作网页 DOM，无法影响浏览器 UI
- 试图通过 CSS/JS（包括 `:fullscreen` 等）隐藏该提示在主流 Edge 版本中不可行

## 可替代方案

- 优先使用 Bilibili 播放器的“网页全屏”而非浏览器“真全屏”（通常不会触发浏览器系统提示）
- 若你需要隐藏浏览器 UI，需要从浏览器设置/策略/实验选项方向尝试，但其可用性随版本变化且可能影响安全性

## 本仓库包含内容

- 文档：原因分析、验证方法与 FAQ（见 [docs](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/docs)）
- 示例扩展骨架：保留 MV3 目录结构，用于演示注入与调试流程（不再承诺可隐藏系统提示）

## 环境依赖

- Google Chrome / Microsoft Edge 最新稳定版
- 可选：Mozilla Firefox（计划支持，需按 Firefox MV3/兼容策略调整）

## 快速开始（本地加载）

1. 克隆仓库

   ```bash
   git clone <your-repo-url>
   cd bilibili-fullscreen-blocker
   ```

2. 打开浏览器扩展管理页
   - Chrome：`chrome://extensions`
   - Edge：`edge://extensions`

3. 打开“开发者模式”，选择“加载已解压的扩展程序”

4. 选择本仓库下的 [extension](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/extension) 目录

5. 打开任意 Bilibili 页面进入全屏，观察提示行为并对照文档结论

## 项目结构（概要）

- [extension](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/extension)：可直接加载/打包发布的扩展产物（Manifest + content script）
- [src](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/src)：源码目录（预留后续构建/多文件拆分）
- [docs](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/docs)：使用/开发/发布等文档
- [tests](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/tests)：测试说明与用例占位
- [assets](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/assets)：资源占位（图标等）
- [config](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/config)：配置占位（未来可加入 lint/format/build 配置）

## 开发与维护

- 以 Manifest V3 为准，扩展可直接从 `extension/` 目录加载用于调试与复现
- 若未来要实现“绕开系统提示”的体验优化，建议走“网页全屏替代真全屏”的方向，并在文档中明确边界

## 发布（打包）

- 若仅作为文档与示例扩展骨架使用，可不发布到商店
- 如需发布，必须在商店描述中明确系统级全屏提示无法被隐藏，避免误导用户（见 [docs/release](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/docs/release.md)）

## 贡献

请先阅读 [CONTRIBUTING](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/CONTRIBUTING.md)。

## 许可证

本项目采用 MIT License，详见 [LICENSE](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/LICENSE)。
