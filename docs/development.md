# 开发说明

## 结论与边界

- 进入全屏后出现的“bilibili.com — 要退出全屏，请按 esc”等提示属于浏览器系统级 UI，不在网页 DOM 中
- content script 与油猴脚本只能操作网页 DOM，无法隐藏浏览器 UI
- 因此本仓库不再以“可隐藏系统级提示”为目标

## 如何快速判断提示是否为浏览器 UI

- 提示覆盖在开发者工具界面之上
- Elements 面板无法选中对应节点
- Console 中对 DOM 的查询无法找到该提示

## 目录约定

- 扩展最终产物以 [extension](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/extension) 为准
- 源码建议维护在 [src](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/src)，必要时同步到 `extension/`
