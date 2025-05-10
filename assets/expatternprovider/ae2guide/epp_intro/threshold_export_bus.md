---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME阈值输出总线
    icon: expatternprovider:threshold_export_bus
categories:
- extended devices
item_ids:
- expatternprovider:threshold_export_bus
---

# ME阈值输出总线

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_threshold_export_bus.snbt"></ImportStructure>
</GameScene>

ME阈值输出总线根据ME网络存储量智能控制物流输出：
- 当指定物品存储量高于/低于设定阈值时激活输出
- 支持双模式切换（阈值上限/下限）

## 工作示例

![GUI](../pic/thr_bus_gui1.png)

铜锭阈值设为128（上限模式）：
- 当网络铜锭存储量＞128时执行输出

![GUI](../pic/thr_bus_gui2.png)

保持128阈值（下限模式）：
- 当网络铜锭存储量＜128时执行输出