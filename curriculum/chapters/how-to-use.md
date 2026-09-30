# 怎么用这套知识库

## 阅读顺序（建议）

1. [知识网络首页](#home) — 站位与地图  
2. [物理家族地图](#physics-map) → [物理时间脉络](#physics-timeline)  
3. [光照时间脉络](#lighting-timeline) → [PBR·光追·Lumen](#pbr-rt-lumen)  
4. [其它支柱](#other-pillars) — 知道还有哪些分支  
5. [每日候选项](#watchlist) / [分档论文](#paper-index) — 跟新文

## 分档含义

| 档 | 含义 |
|----|------|
| **A** | 主张清晰，有对照或强影响力；尽量有核心介绍 |
| **B** | 有实证，但样本/外推/复现有软肋 |
| **C** | 愿景、技术报告，或与主线关联偏弱 |

评级基于摘要级审阅，不是全文同行评审。

## 日更怎么来的

`scripts/monitor_papers.py` 每天从 arXiv / Semantic Scholar / DBLP 拉候选，写入：

- `indexes/game-tech/watchlist.json`
- `indexes/game-tech/inbox/YYYY-MM-DD.json`

**不会自动入库**。正式入库：

```bash
python indexes/game-tech/_add_paper.py --arxiv-id ... --title "..." --tier B --tier-reason "..." --tags physics,mpm
python scripts/build_site.py
```

## 本地预览

```bash
python scripts/build_site.py
python -m http.server 8080 --directory site
```

打开 `http://localhost:8080`。

## 关键要点

- 教程章节是骨架；论文按 `tags` / `knowledge_ids` 挂到章节。
- 日更先看候选项，再人工或 Agent 分档入库。
