---
navigation:
  parent: epp_intro/epp_intro-index.md
  title: ME阈值发信器
  icon: expatternprovider:threshold_level_emitter
categories:
- extended devices
item_ids:
- expatternprovider:threshold_level_emitter
---

# ME阈值发信器

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_threshold_level_emitter.snbt"></ImportStructure>
</GameScene>

它的工作原理类似于重置-置位锁存器。当网络中某种物品的数量低于下限阈值时，它会关闭红石信号；当数量高于上限阈值时，它会开启红石信号。

## 工作原理
本设备基于重置-置位锁存器（Reset-Set Latch）机制工作：
- 当网络物品量＜下限阈值：关闭红石信号
- 当物品量＞上限阈值：激活红石信号
- 在阈值区间内保持当前状态

## 工作示例
设定下限100，上限150：

1. **初始空置状态**（存储量=0）
   - 发信器保持休眠

2. **存储增长阶段**（物品量≥150）
   - 激活红石信号输出

3. **存储波动阶段**（100＜物品量＜150）
   - 维持最近激活状态

4. **存储枯竭阶段**（物品量≤100）
   - 终止红石信号
