# GitHub Practice

这是一个用于练习 GitHub CLI (`gh`) 命令和自动化工作流的仓库。

## 📖 项目目的

本项目旨在帮助开发者：
- 熟悉 GitHub CLI 的各种命令和用法
- 学习自动化工作流的设计与实现
- 掌握 Issue 和 PR 的批量操作技巧
- 了解 GitHub Actions 的监控和管理

## 🎯 学习目标

- [x] 掌握 GitHub CLI 基础命令
- [x] 学会批量操作 Issues
- [ ] 练习 PR 工作流
- [ ] 了解 GitHub Actions 监控
- [ ] 使用 gh-issues 自动修复

## 🚀 使用方法

### 前置要求

```bash
# 安装 GitHub CLI
brew install gh  # macOS
# 或
apt install gh   # Ubuntu

# 认证
gh auth login
```

### 常用命令

```bash
# 查看仓库
gh repo view owner/repo

# 列出 Issues
gh issue list --repo owner/repo --state open

# 创建 Issue
gh issue create --title "Bug title" --body "Description"

# 批量操作
gh issue edit 1 2 3 --add-label "bug"
```

## 📚 练习内容

### 模块 1：GitHub CLI 基础
- 查看仓库信息
- 列出/创建/关闭 Issues
- 查看提交历史

### 模块 2：批量操作
- 批量添加标签
- 批量分配 Issues
- 批量关闭 Issues

### 模块 3：PR 自动化
- 创建 PR
- 审查 PR
- 合并 PR

### 模块 4：GitHub Actions
- 查看工作流
- 触发工作流
- 查看运行日志

### 模块 5：gh-issues 自动修复
- 配置自动修复
- 处理 Issues
- 创建修复 PR

## 🤝 贡献指南

欢迎贡献！请遵循以下步骤：

1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'feat: add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

### 提交规范

使用 [Conventional Commits](https://www.conventionalcommits.org/)：
- `feat:` 新功能
- `fix:` Bug 修复
- `docs:` 文档更新
- `refactor:` 代码重构
- `test:` 测试相关

## 🔗 相关链接

- [GitHub CLI 文档](https://cli.github.com/manual/)
- [GitHub API 文档](https://docs.github.com/rest)
- [gh-issues 技能](~/.openclaw/skills/gh-issues/SKILL.md)

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

---
*Created for GitHub automation learning - 2026-04-25*
*Last updated: 2026-04-25 (fix/issue-3)*
