# 贡献指南

欢迎提交 Issue 与 Pull Request 来改进本项目（例如适配 Bilibili DOM 变化、提升稳定性、补充文档与测试用例）。

## 开发原则

- 保持“只做一件事”：仅拦截/移除全屏提示弹窗，不引入与目标无关的功能
- 权限最小化：如需新增权限，请在 PR 中说明原因并同步更新文档
- 兼容优先：避免影响播放器正常功能与页面交互

## 提交内容要求

- 代码变更需同时更新：
  - 对应文档（若涉及使用方式/权限/发布流程）
  - [CHANGELOG](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/CHANGELOG.md)（若为用户可感知变更）
- 修复选择器变更时，请提供：
  - 旧选择器与新选择器
  - 能复现问题的页面类型（播放页、番剧页、直播页等）

## 提交流程建议

1. Fork 仓库并创建分支
2. 本地加载 [extension](file:///Users/huan.zhang/Code/bilibili-fullscreen-blocker/extension) 目录验证效果
3. 提交 PR，并在描述中说明：
   - 变更动机
   - 测试场景与预期结果
   - 是否涉及权限变更
