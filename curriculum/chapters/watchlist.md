# 每日候选项

监控脚本写入的候选论文会出现在本章下方（构建时读取 `watchlist.json`）。

## 处理流程

1. 看标题/摘要是否贴合物理、渲染或相关标签  
2. 用 `_add_paper.py` 分档入库并打 tags  
3. 需要 A 档时补 `indexes/game-tech/core/<id>.md`  
4. `python scripts/build_site.py`（Actions 会在监控后自动构建 Pages）
