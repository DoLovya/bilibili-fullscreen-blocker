# 发布流程

本仓库当前以“结论/说明文档项目”为主，不建议以“可隐藏浏览器系统级全屏提示”为卖点发布到商店。

## 打包

1. 确认 [extension](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/extension) 目录内包含最新 `manifest.json` 与 `content.js`
2. 将 `extension/` 目录打包为 ZIP 文件
3. 按浏览器商店提交规范上传 ZIP

## 发布前检查

- 在 Chrome/Edge 最新稳定版完成自测（见 [quick-start](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/docs/quick-start.md)）
- 确认权限与文档一致（见 [permissions](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/docs/permissions.md)）
- 变更已写入 [CHANGELOG](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/CHANGELOG.md)

## 商店描述建议

- 明确声明：浏览器系统级全屏提示属于浏览器 UI，不在网页 DOM 中，无法通过扩展内容脚本隐藏
