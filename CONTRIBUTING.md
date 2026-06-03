# 贡献指南 / Contributing Guide

感谢您对本项目的关注！以下是参与贡献的流程和规范。

## 行为准则 / Code of Conduct

- 保持专业和尊重他人的沟通方式
- 建设性地提出意见和建议
- 接受建设性反馈

## 如何贡献 / How to Contribute

### 报告 Bug

1. 在 [Issues](../../issues) 页面搜索是否已有类似问题
2. 如无，请创建新 Issue，包含：
   - Bug 描述
   - 复现步骤
   - 预期行为 vs 实际行为
   - 浏览器版本和操作系统信息
   - 截图（如适用）

### 功能建议

1. 在 [Issues](../../issues) 页面搜索是否已有类似建议
2. 创建新 Issue，描述：
   - 功能需求
   - 使用场景
   - 预期效果

### 提交代码 / Pull Request

1. **Fork** 本仓库
2. 创建功能分支：`git checkout -b feature/your-feature-name`
3. 提交你的更改：`git commit -m 'feat: add your feature description'`
4. 推送到分支：`git push origin feature/your-feature-name`
5. 创建 Pull Request

## 分支管理策略 / Branch Strategy

| 分支 | 用途 |
|------|------|
| `main` | 稳定发布版本，只接受经过审查的 PR |
| `develop` | 开发分支，日常开发合并目标 |
| `feature/*` | 功能开发分支，从 `develop` 分出 |
| `fix/*` | Bug 修复分支，从 `develop` 分出 |
| `docs/*` | 文档更新分支 |

## 代码规范 / Coding Standards

### HTML
- 使用语义化标签
- 保持 2 空格缩进
- 属性使用双引号

### CSS
- 使用 CSS 变量（`--var-name`）进行主题化
- 避免深层嵌套选择器（最多 3 层）
- 类名使用小写 + 连字符（kebab-case）

### JavaScript
- 使用 ES5 兼容语法以确保最大兼容性
- 变量声明使用 `var`
- 函数命名使用 camelCase
- 类命名使用 PascalCase
- 常量使用 UPPER_SNAKE_CASE
- 保持单文件架构，避免不必要的模块拆分

### 提交信息规范 / Commit Message Convention

遵循 [Conventional Commits](https://www.conventionalcommits.org/) 规范：

```
<type>: <description>

[optional body]

[optional footer]
```

**类型 (type):**
- `feat`: 新功能
- `fix`: Bug 修复
- `docs`: 文档更新
- `style`: 代码格式调整（不影响功能）
- `refactor`: 代码重构
- `perf`: 性能优化
- `test`: 测试相关
- `chore`: 构建/工具链变更

**示例:**
```
feat: add target classification panel
fix: resolve threat board flickering on high refresh rate
docs: update README with installation guide
```

## 开发环境 / Development Setup

本项目为零依赖纯前端项目，无需安装任何工具：

1. 克隆仓库
2. 在浏览器中打开 `index.html`
3. 或运行本地服务器：`python -m http.server 8080 --directory .`

## 审查流程 / Review Process

1. 所有 PR 需要至少一位维护者审查
2. CI 检查必须通过
3. 代码需符合上述规范
4. 新功能需包含基本的功能验证说明