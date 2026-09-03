# 大数据与人工智能课程作业

本课程仓库用于存放《大数据与人工智能》课程的各项作业，包含代码、实验报告与相关文档。

## 目录结构

每次作业一个独立目录，命名规则 `assignment-<序号>-<主题>`：

```
bigdata-ai-coursework/
├── README.md
├── .gitignore
├── assignment-01-wordcount/
│   ├── src/           # 源代码
│   ├── data/          # 数据集（不提交到 Git）
│   └── report.md      # 实验报告
└── assignment-02-ml/
```

## 环境

- Python 3.12
- 依赖统一放在各作业目录下的 `requirements.txt`

## Git 常用命令速查

```bash
git status                 # 查看当前改动
git add .                  # 把所有改动加入暂存区
git commit -m "提交说明"    # 打一个本地存档点
git push                   # 推送到 GitHub
git pull                   # 拉取远程最新内容
git log --oneline          # 查看提交历史
```

**良好的提交说明**：`assignment-01: 完成词频统计` —— 说明改了什么、为什么改，不要写 `update`、`修改` 这类无信息量的内容。
