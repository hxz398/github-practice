# GitHub Practice API 文档

本文档描述 GitHub Practice 项目的 API 接口说明。

## 📋 概述

GitHub Practice 是一个用于学习 GitHub CLI 自动化的练习项目。本文档提供主要操作接口的说明。

---

## 🔌 接口列表

### 1. Issue 操作

#### 创建 Issue

```bash
gh issue create --title "<title>" --body "<description>" [options]
```

**参数说明：**

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `--title` | string | ✅ | Issue 标题 |
| `--body` | string | ✅ | Issue 内容 |
| `--label` | string | ❌ | 标签（逗号分隔） |
| `--assignee` | string | ❌ | 分配人 |

**返回值示例：**

```
https://github.com/owner/repo/issues/123
```

---

#### 列出 Issues

```bash
gh issue list [options]
```

**参数说明：**

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `--state` | string | ❌ | 状态：open, closed, all |
| `--label` | string | ❌ | 按标签过滤 |
| `--limit` | number | ❌ | 最大数量 |
| `--assignee` | string | ❌ | 按分配人过滤 |

**返回值示例：**

```
123	OPEN	Bug title	bug	2026-04-25T06:00:00Z
122	OPEN	Feature request	enhancement	2026-04-24T12:00:00Z
```

---

#### 批量编辑 Issues

```bash
gh issue edit <numbers...> [options]
```

**参数说明：**

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `numbers` | number[] | ✅ | Issue 编号列表 |
| `--add-label` | string | ❌ | 添加标签 |
| `--remove-label` | string | ❌ | 移除标签 |
| `--add-assignee` | string | ❌ | 添加分配人 |

**返回值示例：**

```
https://github.com/owner/repo/issues/123
https://github.com/owner/repo/issues/122
```

---

### 2. Pull Request 操作

#### 创建 PR

```bash
gh pr create --title "<title>" --body "<description>" [options]
```

**参数说明：**

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `--title` | string | ✅ | PR 标题 |
| `--body` | string | ✅ | PR 描述 |
| `--base` | string | ❌ | 目标分支（默认 main） |
| `--head` | string | ❌ | 源分支 |
| `--label` | string | ❌ | 标签 |

**返回值示例：**

```
https://github.com/owner/repo/pull/456
```

---

#### 审查 PR

```bash
gh pr review <number> [options]
```

**参数说明：**

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `number` | number | ✅ | PR 编号 |
| `--approve` | flag | ❌ | 批准 |
| `--request-changes` | flag | ❌ | 请求修改 |
| `--comment` | flag | ❌ | 仅评论 |
| `--body` | string | ❌ | 评论内容 |

**返回值示例：**

```
✓ Review submitted
```

---

### 3. GitHub API 查询

#### 直接 API 调用

```bash
gh api <endpoint> [options]
```

**参数说明：**

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `endpoint` | string | ✅ | API 端点 |
| `--jq` | string | ❌ | jq 过滤表达式 |
| `--method` | string | ❌ | HTTP 方法 |
| `-f` | key=value | ❌ | 表单字段 |

**常用端点：**

| 端点 | 说明 |
|------|------|
| `user` | 当前用户信息 |
| `repos/{owner}/{repo}` | 仓库信息 |
| `repos/{owner}/{repo}/issues` | Issues 列表 |
| `repos/{owner}/{repo}/pulls` | PRs 列表 |
| `search/issues?q=...` | 搜索 Issues |

**返回值示例：**

```json
{
  "login": "hxz398",
  "public_repos": 2,
  "followers": 0
}
```

---

## 📊 状态码说明

| 状态码 | 说明 |
|--------|------|
| 200 | 成功 |
| 201 | 已创建 |
| 400 | 请求错误 |
| 401 | 未授权 |
| 403 | 禁止访问 |
| 404 | 未找到 |
| 422 | 参数验证失败 |

---

## 🔐 认证

所有 API 调用需要先进行认证：

```bash
gh auth login
gh auth status
```

---

## 📚 相关链接

- [GitHub CLI 手册](https://cli.github.com/manual/)
- [GitHub REST API](https://docs.github.com/rest)
- [jq 手册](https://stedolan.github.io/jq/manual/)

---
*Generated: 2026-04-25*
*For Issue #2: Docs: 添加 API 文档*
