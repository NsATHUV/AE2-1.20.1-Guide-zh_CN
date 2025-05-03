---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 触发总线
  icon: toggle_bus
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:toggle_bus
- ae2:inverted_toggle_bus
---

# 触发总线

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/toggle_bus.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

该总线功能类似<ItemLink id="fluix_glass_cable" />（福鲁伊克斯玻璃线缆）等线缆，但可通过红石信号切换连接状态。可用于切断[ME网络](../ae2-mechanics/me-network-connections.md)的特定区段。

当接收到红石信号时，<ItemLink id="toggle_bus" />会激活连接；而<ItemLink id="inverted_toggle_bus" />（反相触发总线）则会在信号激活时禁用连接。

注意：切换连接可能导致网络重启并重新计算连接设备。

触发总线属于[线缆子部件](../ae2-mechanics/cable-subparts.md)。

## 合成配方

<RecipeFor id="toggle_bus" />

<RecipeFor id="inverted_toggle_bus" />