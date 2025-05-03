---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 网络工具
  icon: network_tool
  position: 410
categories:
- tools
item_ids:
- ae2:network_tool
---

# 网络工具

<ItemImage id="network_tool" scale="4" />

网络工具是改良版[石英扳手](wrench.md)，兼具网络诊断功能和[升级卡](upgrade_cards.md)存储能力。保留快速拆卸设备和移除线缆[子部件](../ae2-mechanics/cable-subparts.md)的功能，但无法旋转方块。

内置9个升级卡槽位，当工具在物品栏时，所有AE2设备界面均可访问这些升级卡。

右键点击网络任意部分将显示诊断窗口（类似右键<ItemLink id="controller" />），包含：
* 网络中已使用的频道数
* 全局能源单位切换（AE/E/FE）
* 网络存储的[能源](../ae2-mechanics/energy.md)量及最大容量
* 能源输入/消耗速率
* 网络中所有[设备](../ae2-mechanics/devices.md)和组件的列表

该窗口在调试[子网](../ae2-mechanics/subnetworks.md)时，可帮助确认不同线缆/设备是否属于同一网络。

## 隐藏伪装板

手持网络工具时，<a href="facades.md">伪装板</a>将被隐藏。

此时可直接与伪装板后方的方块交互，无需先行移除伪装板。

## 合成配方

<RecipeFor id="network_tool" />