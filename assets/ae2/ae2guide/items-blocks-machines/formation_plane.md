---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 成型面板
  icon: formation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:formation_plane
---

# 成型面板

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/formation_plane.snbt" />
</GameScene>

成型面板用于放置方块和丢弃物品。其功能类似仅允许存入的<ItemLink id="storage_bus" />，当[设备](../ae2-mechanics/devices.md)（如<ItemLink id="import_bus" />和<ItemLink id="interface" />）向[网络存储](../ae2-mechanics/import-export-storage.md)存入物品时触发放置/丢弃操作。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/formation_plane_demonstration.snbt" />
  <IsometricCamera yaw="255" pitch="30" />
</GameScene>

该[设备](../ae2-mechanics/devices.md)利用了[管道子网](../example-setups/pipe-subnet.md)中存储总线的机制，若需要丢弃物品/放置方块而非运输物品，可用其替代存储总线。

成型面板属于[线缆子部件](../ae2-mechanics/cable-subparts.md)。

**请确保在领地插件中启用假玩家权限**

## 过滤设置

默认情况下会放置/丢弃所有物品。在过滤槽中放入物品将启用白名单模式，仅允许指定物品被放置。

即使未实际拥有某物品，仍可通过JEI/REI将其拖入过滤槽。

右键点击流体容器（如桶或储罐）可设置流体过滤器而非容器物品本身。

## 优先级

点击GUI右上角的扳手图标可设置优先级。物品进入网络时将优先存入最高优先级的存储设备。

## 设置项

* 可配置为在世界上放置方块或直接丢弃物品

## 可安装升级

成型面板支持以下[升级卡](upgrade_cards.md)：
* <ItemLink id="capacity_card" /> 增加过滤槽数量
* <ItemLink id="fuzzy_card" /> 启用按耐久度过滤或忽略物品NBT
* <ItemLink id="inverter_card" /> 将过滤模式切换为黑名单

## 合成配方

<RecipeFor id="formation_plane" />