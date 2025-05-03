---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME存储总线
  icon: storage_bus
  position: 220
categories:
- devices
item_ids:
- ae2:storage_bus
---

# 存储总线

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/storage_bus.snbt" />
</GameScene>

是否希望保留你的"箱子怪兽"而不是替换成更合理的存储方案？存储总线正是为此而生！

存储总线能将相邻的容器转变为[网络存储](../ae2-mechanics/import-export-storage.md)。
它通过以下方式实现：让网络能够查看该容器的内容，并通过推入/拉取物品来响应其他[设备](../ae2-mechanics/devices.md)对网络存储的操作。

基于AE2"通过设备交互实现复合功能"的设计理念，存储总线并非只能用于*存储*。通过[子网络](../ae2-mechanics/subnetworks.md)将存储总线设置为网络中*唯一*的存储设备，可将其作为物品传输的源头或终点（参见["管道子网"示例](../example-setups/pipe-subnet.md)）。

存储总线属于[线缆子部件](../ae2-mechanics/cable-subparts.md)。

## 过滤功能

默认情况下总线会存储所有物品。在过滤槽中放置物品可设为白名单模式，仅允许存储指定物品。

即使当前未拥有某物品，仍可通过JEI/REI将物品或流体拖入过滤槽（流体需通过容器设置）。

右键使用流体容器（如桶或储罐）可将流体设为过滤器而非容器本身。

## 优先级

通过点击GUI右上角的扳手图标设置优先级。
物品进入网络时会优先存入最高优先级的存储。当多个存储优先级相同时：
- 若某个存储已存在该物品，则优先选择该存储
- 在相同优先级组中，已设置过滤的存储会被视为"已包含过滤物品"
物品取出时会优先从最低优先级的存储提取。该机制使高优先级存储被优先填充，低优先级存储被优先清空。

## 设置选项

* 可根据相邻容器当前内容进行分区（过滤）
* 可设置是否允许网络查看总线无法提取的容器内物品（例如存储总线无法从<ItemLink id="inscriber" />的中部输入槽提取物品）
* 可设置过滤应用于存入/取出或仅存入
* 可设置为双向、仅存入或仅取出模式

## 升级卡支持

存储总线支持以下[升级卡](upgrade_cards.md)：

* <ItemLink id="capacity_card" />：增加过滤槽数量
* <ItemLink id="fuzzy_card" />：支持按耐久度过滤或忽略物品NBT
* <ItemLink id="inverter_card" />：将过滤模式从白名单切换为黑名单
* <ItemLink id="void_card" />：当相邻容器满时销毁多余物品，防止生产设施堵塞（需谨慎设置过滤）

## 合成配方

<RecipeFor id="storage_bus" />