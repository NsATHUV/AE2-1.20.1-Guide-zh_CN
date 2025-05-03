---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME驱动器
  icon: drive
  position: 210
categories:
- 设备
item_ids:
- ae2:drive
---

# ME驱动器

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/drive.snbt" />
</GameScene>

该设备用于接入[存储元件](storage_cells.md)，为[网络存储系统](../ae2-mechanics/import-export-storage.md)提供容量支持。驱动器提供10个槽位，每个槽位可容纳一个存储元件。

可通过漏斗或AE2总线等物流系统对驱动器槽位内的元件进行存取操作。

使用<ItemLink id="certus_quartz_wrench" />可调整设备朝向。

## 元件状态指示灯

驱动器槽位配备LED指示灯显示存储状态：

| 颜色   | 状态描述                                                                       |
| :----- | :----------------------------------------------------------------------------- |
| 绿色   | 元件空置                                                                       |
| 蓝色   | 元件已存储部分物品                                                             |
| 橙色   | [类型容量](../ae2-mechanics/bytes-and-types.md)已满，无法添加新类型物品       |
| 红色   | [字节容量](../ae2-mechanics/bytes-and-types.md)已满，无法存入更多物品         |
| 黑色   | 设备断电或未分配[频道](../ae2-mechanics/channels.md)                           |

## 优先级设置

通过点击GUI右上角的扳手图标可设置存储优先级。物品存入网络时会优先选择最高优先级的存储位置。当多个存储设备优先级相同时：

- 若某存储已存在该物品，则优先选择该存储
- [分区存储元件](cell_workbench.md)在相同优先级组中会被视为已包含分区物品
- 取出物品时优先从最低优先级的存储中移除

该机制将确保高优先级存储优先填满，低优先级存储优先清空。

## 配方

<RecipeFor id="drive" />