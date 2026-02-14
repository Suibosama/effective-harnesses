# /harness-init 命令

## 功能

初始化一个新的开发项目，创建完整的框架结构。

## 执行步骤

### 1. 检查当前目录状态

```bash
ls -la
```

确认这是一个新项目目录（没有 feature_list.json）。

### 2. 收集项目信息

使用 AskUserQuestion 询问：
- 项目名称
- 开发服务器启动命令（如 `npm run dev`、`python manage.py runserver` 等）
- 项目描述（可选）

### 3. 创建 init.sh 脚本

创建 `init.sh` 文件，包含用户提供的启动命令：

```bash
#!/bin/bash
# 项目启动脚本
npm run dev
```

确保脚本可执行：
```bash
chmod +x init.sh
```

### 4. 初始化 Git 仓库

如果尚未初始化 Git：

```bash
git init
git add .
git commit -m "Initial commit: project initialization"
```

### 5. 创建 feature_list.json

```json
{
  "version": "1.0",
  "project": "项目名称",
  "created": "2026-02-14",
  "features": []
}
```

### 6. 创建 claude-progress.txt

```
# Claude Progress Log

## Project: 项目名称
Created: 2026-02-14

## History
- 2026-02-14: Project initialized
```

### 7. 提交初始文件

```bash
git add .
git commit -m "Add: effective-harnesses framework files"
```

## 输出

完成初始化后，显示：
- 创建的文件列表
- 下一步建议（添加第一个 feature）
