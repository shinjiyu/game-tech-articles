# game-tech-articles

**游戏技术知识网络**：物理模拟 × 实时渲染（及相邻支柱）知识点 + 持续更新的论文索引（分档 A/B/C、入库时间、A 档核心介绍）。

站点框架对齐 [agent-harness-articles](https://github.com/shinjiyu/agent-harness-articles)：日更监控候选项，GitHub Actions **在同一次流水线里构建并发布 Pages**（避免 `GITHUB_TOKEN` push 无法触发第二个 workflow 的问题）。

## 快速入口

| 用途 | 路径 |
|------|------|
| 学习站 | [`site/`](site/) |
| 知识点 | [`curriculum/`](curriculum/) |
| 论文索引 | [`indexes/game-tech/`](indexes/game-tech/) |
| 构建 | [`scripts/build_site.py`](scripts/build_site.py) |

Pages：https://shinjiyu.github.io/game-tech-articles/

## 本地预览

```bash
python scripts/build_site.py
python -m http.server 8080 --directory site
```

## 论文监控

```bash
python scripts/monitor_papers.py
```

候选项写入 `watchlist.json` / `inbox/`，**不自动入库**。入库：

```bash
python indexes/game-tech/_add_paper.py --arxiv-id ... --title "..." --tier B --tier-reason "..." --tags physics,mpm
python scripts/build_site.py
```

## 分档

| 档 | 含义 |
|----|------|
| **A** | 主张清晰，影响大或有对照；含核心介绍 |
| **B** | 有实证，外推/复现有软肋 |
| **C** | 愿景、工业文档或关联偏弱 |

## 与 agent-harness-articles 的差异

- 主题换成游戏图形物理 / 渲染知识网络。  
- 监控 workflow **同 job 内 deploy Pages**，日更候选项会反映到站点「每日候选项」章。
