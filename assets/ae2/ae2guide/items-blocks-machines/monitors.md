---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 监控器
  icon: storage_monitor
  position: 210
categories:
- devices
item_ids:
- ae2:storage_monitor
- ae2:conversion_monitor
---

# ME监控器

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/monitors.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

监控器可在不打开GUI的情况下展示并操作单一物品或流体类型。

监控器颜色继承其所在[线缆](cables.md)的颜色。

若安装在地面或天花板，可使用<ItemLink id="certus_quartz_wrench" />旋转方向。

该设备属于[线缆子部件](../ae2-mechanics/cable-subparts.md)。

# ME存储监控器

显示指定物品/流体及其存储数量。可安装于自动化农场等区域作为可视化指示器。

*无需*占用[频道](../ae2-mechanics/channels.md)。

操作指令：
* 右键持有物品/双击流体容器：设置监控物品
* 空手右键：清空监控目标
* Shift+空手右键：锁定当前配置

## 合成配方

<RecipeFor id="storage_monitor" />

# ME交换监控器

在存储监控功能基础上，支持物品存取操作。当配置物品[可自动合成](../ae2-mechanics/autocrafting.md)且库存为零时，提取操作将触发合成界面。

*需要*占用[频道](../ae2-mechanics/channels.md)。

扩展操作指令：
* 左键点击：提取整组物品（库存不足时触发合成）
* 持有物品右键：存入物品
* 空手右键：存入背包中所有匹配物品

## 合成配方

<RecipeFor id="conversion_monitor" />