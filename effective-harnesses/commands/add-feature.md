# /harness-add 命令

## 功能

向 feature_list.json 添加新的 feature。

## 执行步骤

### 1. 确认项目已初始化

检查是否存在 feature_list.json：

```bash
ls feature_list.json
```

如果不存在，提示用户先运行 `/harness-init`。

### 2. 收集 Feature 信息

使用 AskUserQuestion 收集以下信息：

1. **Category 类型**
   - functional (新功能)
   - bugfix (Bug 修复)
   - refactor (重构)

2. **Feature 描述**
   - 简短描述这个 feature 要做什么

3. **实现步骤**
   - 列出实现这个功能需要的主要步骤（最多 5 个）

4. **优先级**
   - 1 (高)
   - 2 (中)
   - 3 (低)

### 3. 读取现有 feature_list.json

```bash
Read feature_list.json
```

### 4. 生成新 Feature ID

根据现有 features 数量生成 ID：
- 第一个: feat-001
- 第二个: feat-002
- 以此类推

### 5. 添加新 Feature

更新 feature_list.json，添加新 feature：

```json
{
  "id": "feat-XXX",
  "category": "functional",
  "priority": 1,
  "description": "描述",
  "steps": ["步骤1", "步骤2"],
  "status": "pending",
  "passes": false
}
```

### 6. 提交更改

```bash
git add feature_list.json
git commit -m "Add: feature-description"
```

## 输出

显示新添加的 feature 信息：
- Feature ID
- 描述
- 优先级
- 建议的下一步操作
