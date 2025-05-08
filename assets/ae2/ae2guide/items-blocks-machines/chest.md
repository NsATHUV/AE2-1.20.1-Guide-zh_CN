---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME箱子
  icon: chest
  position: 210
categories:
- devices
item_ids:
- ae2:chest
---

# ME箱子

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/chest.snbt" />
</GameScene>

ME箱子集成了<ItemLink id="terminal" />、<ItemLink id="drive" />和<ItemLink id="energy_acceptor" />，相当于微型网络。由于仅支持单个[存储元件](../items-blocks-machines/storage_cells.md)，其独立存储能力有限。

核心功能：通过内置终端直接管理插入的存储元件。主网络中的[设备](../ae2-mechanics/devices.md)可通过[网络存储](../ae2-mechanics/import-export-storage.md)访问ME箱子内容。

## 交互方式

* **顶部面**：打开集成终端（仅允许存入物品）
* **其他面**：显示存储元件插槽和优先级设置（支持物流设备存取）
* 使用<ItemLink id="certus_quartz_wrench" />调整设备朝向

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/chest_color.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 技术参数

* 内置小型AE能源缓冲（未连接[能源元件](../items-blocks-machines/energy_cells.md)时，高频存取可能断电）
* 使用<ItemLink id="color_applicator" />可改变终端颜色
* 支持与普通终端相同的设置（不支持<ItemLink id="view_cell" />）

## 元件状态指示灯

| 颜色   | 状态描述                  |
| :----- | :----------------------- |
| 绿色   | 元件为空                  |
| 蓝色   | 元件有存储内容            |
| 橙色   | [类型容量](../ae2-mechanics/bytes-and-types.md)已满 |
| 红色   | [存储容量](../ae2-mechanics/bytes-and-types.md)已满 |
| 黑色   | 断电或未分配[频道](../ae2-mechanics/channels.md) |

## 优先级设置

点击元件插槽界面右上角扳手图标设置优先级：
- **存入逻辑**：物品优先进入最高优先级存储
- **同类优先**：同优先级时优先已有该物品的存储
- **分区优先**：分区元件在同优先级组中视为已包含物品
- **取出逻辑**：优先从最低优先级存储提取

## 合成配方

<RecipeFor id="chest" />