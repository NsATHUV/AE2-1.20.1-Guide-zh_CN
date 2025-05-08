---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 压印器
  icon: inscriber
  position: 310
categories:
- machines
item_ids:
- ae2:inscriber
---

# 压印器

<BlockImage id="inscriber" scale="8" />

压印器用于通过[压印模板](presses.md)刻印电路和[处理器](processors.md)，并将各种物品粉碎成粉末。
可接受AE2能源（AE）或Fabric/Forge Energy（E/FE）。支持分面输入，不同面可插入不同槽位物品。可通过<ItemLink id="certus_quartz_wrench" />旋转方向。支持将合成产物推入相邻容器。

输入缓冲区大小可调节。例如在批量压印阵列中，小缓冲区能优化材料分配（避免首个压印器装满64个而其他空闲）。

四种电路压印模板用于制作[处理器](processors.md):

<Row>
  <ItemImage id="silicon_press" scale="4" />

  <ItemImage id="logic_processor_press" scale="4" />

  <ItemImage id="calculation_processor_press" scale="4" />

  <ItemImage id="engineering_processor_press" scale="4" />
</Row>

名称压印模板可为方块命名（类似铁砧），适用于<ItemLink id="pattern_access_terminal" />中的标记：

<ItemImage id="name_press" scale="4" />

## 设置项

* 可切换分面模式（特定面输入）或非分面模式（任意面输入，自动分拣）。非分面模式下无法从顶部/底部槽取出物品
* 可启用向相邻容器推送物品
* 输入缓冲区大小可调节：大缓冲区适合手动操作，小缓冲区适合并行阵列

## GUI界面与分面输入

分面模式下，不同面的输入/输出对应不同槽位：

![压印器GUI](../assets/diagrams/inscriber_gui.png) ![压印器分面示意图](../assets/diagrams/inscriber_sides.png)

A. **顶部输入槽** - 通过设备顶部面存取（可输入/输出）

B. **中部输入槽** - 通过左右前后四面输入（仅限输入，不可输出）

C. **底部输入槽** - 通过设备底部面存取（可输入/输出）

D. **输出槽** - 通过左右前后四面输出（仅限输出，不可输入）

## 简单自动化示例

利用分面模式和可旋转性实现半自动化：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/inscriber_hopper_automation.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

非分面模式下可直接通过管道输入输出

## 可安装升级

压印器支持以下[升级卡](upgrade_cards.md)：
* <ItemLink id="speed_card" />（加速卡）

## 合成配方

<RecipeFor id="inscriber" />