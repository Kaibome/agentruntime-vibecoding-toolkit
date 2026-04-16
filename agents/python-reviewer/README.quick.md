# Python Reviewer 团队速查版

## 什么时候用

- 任何 Python 代码改动后
- 提交 PR 前

## 先跑这 3 条

```bash
git diff -- '*.py'
ruff check .
ruff format --check .
```

## 审查优先级（从高到低）

- **CRITICAL（安全）**：SQL/命令注入、路径穿越、`eval/exec`、不安全反序列化、硬编码密钥、弱加密、YAML unsafe load
- **CRITICAL（错误处理）**：裸 `except`、吞异常、未用 `with` 管理资源
- **HIGH（类型）**：公共函数缺类型、滥用 `Any`、缺 `Optional`
- **HIGH（Pythonic）**：可变默认参数、`type()==`、魔法数字、低效字符串拼接、可替换为推导式
- **MEDIUM（性能）**：生成器、`set` 查找、避免循环重复计算、`defaultdict`
- **LOW（风格）**：snake_case、80 列、import 分组顺序

## 输出模板

```text
## 审查结果
### CRITICAL
- [文件:行号] 问题 -> 修复建议
### HIGH
- [文件:行号] 问题 -> 修复建议
### MEDIUM
- [文件:行号] 问题 -> 修复建议
总结：X 个 CRITICAL，Y 个 HIGH，Z 个 MEDIUM
```
