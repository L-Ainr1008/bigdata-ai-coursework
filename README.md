# 大数据与人工智能课程作业

本课程仓库用于存放《大数据与人工智能》课程的各项作业，包含代码、实验报告与相关文档。

## 目录结构

按文件类型组织，四个目录各司其职：

```
bigdata-ai-coursework/
├── README.md
├── .gitignore
├── assignments/      # 作业代码（.py / .scala 等）
├── data/             # 数据集（不上传，见下方说明）
├── notebooks/        # Jupyter 笔记本，用于探索与可视化
└── reports/          # 实验报告（Markdown 或 PDF）
```

**命名建议**：同一份作业的多个文件用统一前缀，方便对应。

```
assignments/hw1_wordcount.py
notebooks/hw1_exploration.ipynb
reports/hw1_report.md
```

**关于 `data/`**：GitHub 单个文件上限 100MB，数据集一律不入库。
目录本身通过 `.gitkeep` 保留在 Git 中，换电脑克隆后文件夹还在，
但里面的数据文件不会上传 —— 数据集请自行保存备份。

## 环境

- Python 3.12
- 依赖统一放在仓库根目录的 `requirements.txt`

## Git 常用命令速查

```bash
git status                 # 查看当前改动
git add .                  # 把所有改动加入暂存区
git commit -m "提交说明"    # 打一个本地存档点
git push                   # 推送到 GitHub
git pull                   # 拉取远程最新内容
git log --oneline          # 查看提交历史
```

**良好的提交说明**：`hw1: 完成词频统计` —— 说明改了什么、为什么改，不要写 `update`、`修改` 这类无信息量的内容。

## 作业索引

- 待补充
