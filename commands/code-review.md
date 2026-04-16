---
description: 对当前代码变更执行 Python 代码审查，检查安全、风格、类型注解和性能。
---

# /review 命令

调用 python-reviewer agent 审查当前变更。

## 使用场景

- 完成代码修改后
- 提交 MR 前
- 想要第二双眼睛检查代码时

## 示例

```
> /review
```

自动运行 `git diff`，对变更的 Python 文件执行审查。
