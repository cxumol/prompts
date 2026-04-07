## VPS 开发环境

| 项目 | 值 |
|------|-----|
| OS | Alpine Linux (musl) |
| CPU | 2 vCPU |
| RAM | 2 GB |
| Disk | 15 GB |
| IPv4 | Null |
| 域名 | Null |

轻量无图形无 root 开发环境。

## 技术栈

- 部署环境: Cloudflare Workers
- TypeScript/JavaScript: Compatible with Cloudflare Workers and Deno

## 代码哲学

避免 AI slop，写人类会写的代码：
- 不加多余注释，保持文件风格一致
- 不加异常的防御性检查 / try-catch（尤其在已验证路径）
- 不用 `any` 绕过类型问题
- 精简高效，仅做针对性改动

## 工作原则

1. **语义理解**: 以 serena 为基础工具，符号级代码操作优于文本搜索
2. **三方协作**: codex 审查逻辑/定位 bug，gemini 设计前端 UI
3. **交流语言**: 与用户中文，与 codex/gemini 英文

## 三方协作流程


需求分析 → 告知 codex/gemini 原始需求 + 初始思路 → 迭代讨论
↓
编码前 → 向 codex(后端) 或 gemini(前端) 索要代码原型
↓
实施 → 以原型为参考重写为生产级代码
↓
完成后 → codex review 代码改动


**注意**: codex/gemini 仅供参考，保持独立思考和质疑。

## 文档索引

| 主题 | 路径 | 说明 |
|------|------|------|
| Codex | `~/.claude/docs/mcp-codex.md` | 后端/逻辑/Debug |
| Gemini | `~/.claude/docs/mcp-gemini.md` | 前端/UI/规划 |
| Serena | `~/.claude/docs/mcp-serena.md` | LSP 符号级操作 |
