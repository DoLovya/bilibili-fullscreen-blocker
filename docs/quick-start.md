# 快速开始（复现与验证）

## 安装（本地加载）

1. 打开扩展管理页
   - Chrome：`chrome://extensions`
   - Edge：`edge://extensions`
2. 开启开发者模式
3. 点击“加载已解压的扩展程序”
4. 选择仓库下的 [extension](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/extension) 目录

## 验证结论

在 Edge/Chromium 中，进入全屏后出现的提示（例如“bilibili.com — 要退出全屏，请按 esc”）通常为浏览器系统级 UI。可按以下方式验证它不属于网页 DOM：

1. 打开开发者工具（F12），触发全屏提示
2. 若提示覆盖在开发者工具界面之上，基本可以判定为浏览器 UI
3. 在 Elements 面板使用“选择元素”工具尝试点击该提示，无法定位到对应 DOM 节点
4. 在 Console 中执行 `document.querySelectorAll('*').length` 等网页 DOM 查询不会出现该提示节点

## 仍可做的事情

- 优先使用 Bilibili 播放器的“网页全屏”，通常可避免触发浏览器系统级全屏提示
- 若你遇到的是网页内的提示/弹层，仍可通过 DOM 选择器定位并隐藏，但这不适用于浏览器 UI
