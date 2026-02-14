# /harness-complete 命令

## 功能

标记指定 feature 为已完成，并更新进度。

## 执行步骤

### 1. 确认项目已初始化

检查 feature_list.json 是否存在。

### 2. 列出所有未完成的 feature

```bash
Read feature_list.json
```

提取所有 passes: false 的 feature。

### 3. 让用户选择要完成的 feature

使用 AskUserQuestion 让用户选择：
- 列出所有未完成的 feature
- 或者选择 "全部完成" 选项

### 4. 验证功能是否真正完成

在标记为完成前，需要验证：

1. **代码完整性**: 所有预期的代码变更都已实现
2. **功能测试**: 功能是否按预期工作
3. **无回归**: 现有功能未被破坏

可以询问用户：
- "功能是否已经实现完成？"
- "是否通过了测试？"

### 5. 更新 feature 状态

对于要完成的 feature：
- 设置 `status: "completed"`
- 设置 `passes: true`
- 记录完成时间（可选）

### 6. 更新进度日志

在 claude-progress.txt 中添加记录：

```
## 2026-02-14
- Completed: feat-001 - 功能描述
```

### 7. Git 提交

```bash
git add feature_list.json claude-progress.txt
git commit -m "Complete: feat-001 - feature description"
```

## 输出

显示已完成的 feature：
- Feature ID
- 描述
- 下一个建议的 feature（如果有）
