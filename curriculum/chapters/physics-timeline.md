# 物理时间脉络与落地

## 时间线

| 年代 | 节点 | 之前/之后 | 落地 |
|------|------|-----------|------|
| 1987–1998 | 力/加速度时代 | 质点弹簧 / 隐式 FEM（Baraff & Witkin 1998 布料） | 离线动画；游戏难稳 |
| 1999–2003 | 网格流体稳定化 | Stam Stable Fluids；SPH 进交互 | 烟雾、早期交互水 |
| 2001 | Jakobsen | Hitman Fysix：Verlet + 位置约束 | 游戏布料/尸体 |
| 2006/07 | **PBD** | Müller et al. 一般化约束投影 | PhysX 等中间件 |
| 2013 | 分水岭 | PBF 液体；Frozen **MPM** 雪 | 游戏液 + 电影雪泥 |
| 2014–2016 | 精炼 | Projective Dynamics；**XPBD** | 现代引擎默认气质 |
| 2018–今 | 连续介质 + 硬接触 | MLS-MPM；**IPC** 族；GPU 布料 | 实时沙水泥、机器人、堆叠 |

## 口诀

- **布料**：显式弹簧 → 隐式 FEM → 游戏改 Jakobsen/PBD → XPBD/PD → 要绝不穿帮再 IPC。  
- **水体**：Stable Fluids/高度场 → SPH → PBF → MPM → 实时 MPM 变体。  
- **碰撞**：惩罚/冲量/LCP → PBD 推出 → IPC 势垒。

## 关键要点

- PBD 正式论文：**2006（VRIPHYS）/ 2007（期刊）**；游戏预告 **Jakobsen 2001**。  
- 交互默认长寿；电影/科研突破常在别的赛道。
