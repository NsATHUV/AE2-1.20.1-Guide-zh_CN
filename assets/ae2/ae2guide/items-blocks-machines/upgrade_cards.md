---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 升级卡
  icon: speed_card
  position: 410
categories:
- tools
item_ids:
- ae2:basic_card
- ae2:advanced_card
- ae2:redstone_card
- ae2:capacity_card
- ae2:void_card
- ae2:fuzzy_card
- ae2:speed_card
- ae2:inverter_card
- ae2:crafting_card
- ae2:equal_distribution_card
- ae2:energy_card
---

# 升级卡系统

<Row>
  <ItemImage id="redstone_card" scale="2" />

  <ItemImage id="capacity_card" scale="2" />

  <ItemImage id="void_card" scale="2" />

  <ItemImage id="fuzzy_card" scale="2" />

  <ItemImage id="speed_card" scale="2" />

  <ItemImage id="inverter_card" scale="2" />

  <ItemImage id="crafting_card" scale="2" />

  <ItemImage id="equal_distribution_card" scale="2" />

  <ItemImage id="energy_card" scale="2" />
</Row>

升级卡用于改变AE2[设备](../ae2-mechanics/devices.md)行为，可提升运行速度、增加过滤容量、启用红石控制等功能。

## 基础组件

<Row>
  <ItemImage id="basic_card" scale="2" />

  <ItemImage id="advanced_card" scale="2" />
</Row>

所有升级卡需使用基础或高级卡基制作：

<Row>
  <RecipeFor id="basic_card" />

  <RecipeFor id="advanced_card" />
</Row>

## 红石卡

<ItemImage id="redstone_card" scale="2" />

为设备添加红石控制功能，在GUI中显示模式切换按钮，支持多种红石信号条件。

<RecipeFor id="redstone_card" />

## 容量卡

<ItemImage id="capacity_card" scale="2" />

提升输入/输出总线、存储总线及成型面板的过滤槽数量。

<RecipeFor id="capacity_card" />

## 溢出销毁卡

<ItemImage id="void_card" scale="2" />

在<ItemLink id="cell_workbench" />中安装至[存储元件](storage_cells.md)后，当元件满载时销毁多余物品（需设置[过滤](cell_workbench.md)）。配合均分卡使用时，即使其他分区未满，特定类型分区满载时也会销毁多余物品。

<RecipeFor id="void_card" />

## 模糊卡

<ItemImage id="fuzzy_card" scale="2" />

允许设备按耐久度过滤或忽略物品NBT数据。示例如下：

| 25%阈值              | 10%耐久镐 | 30%耐久镐 | 80%耐久镐 | 全新镐 |
| ------------------- | -------- | -------- | -------- | ----- |
| 即将损坏的镐          | ✅        |          |          |       |
| 修复完成的镐          |          | ✅        | ✅        | ✅     |

| 50%阈值              | 10%耐久镐 | 30%耐久镐 | 80%耐久镐 | 全新镐 |
| ------------------- | -------- | -------- | -------- | ----- |
| 即将损坏的镐          | ✅        | ✅        |          |       |
| 修复完成的镐          |          |          | ✅        | ✅     |

| 75%阈值              | 10%耐久镐 | 30%耐久镐 | 80%耐久镐 | 全新镐 |
| ------------------- | -------- | -------- | -------- | ----- |
| 即将损坏的镐          | ✅        | ✅        |          |       |
| 修复完成的镐          |          |          | ✅        | ✅     |

| 99%阈值              | 10%耐久镐 | 30%耐久镐 | 80%耐久镐 | 全新镐 |
| ------------------- | -------- | -------- | -------- | ----- |
| 即将损坏的镐          | ✅        | ✅        | ✅        |       |
| 修复完成的镐          |          |          |          | ✅     |

| 忽略耐久              | 10%耐久镐 | 30%耐久镐 | 80%耐久镐 | 全新镐 |
| ------------------- | -------- | -------- | -------- | ----- |
| 即将损坏的镐          | ✅        | ✅        | ✅        | **✅** |
| 修复完成的镐          | **✅**    | **✅**    | **✅**    | ✅     |

<RecipeFor id="fuzzy_card" />

## 加速卡

<ItemImage id="speed_card" scale="2" />

提升设备运行速度：输入/输出总线每次操作传输更多物品，压印器和分子装配室工作更快。

<RecipeFor id="speed_card" />

## 反相卡

<ItemImage id="inverter_card" scale="2" />

将设备的过滤模式从白名单切换为黑名单。

<RecipeFor id="inverter_card" />

## 合成卡

<ItemImage id="crafting_card" scale="2" />

允许设备向[自动合成](../ae2-mechanics/autocrafting.md)系统发送合成请求获取所需物品。

<RecipeFor id="crafting_card" />

## 均分卡

<ItemImage id="equal_distribution_card" scale="2" />

在<ItemLink id="cell_workbench" />中安装至[存储元件](storage_cells.md)后，根据过滤设置将存储空间均分，防止单一类型占满元件。

<RecipeFor id="equal_distribution_card" />

## 能源卡

<ItemImage id="energy_card" scale="2" />

提升便携终端等工具的电池容量，并提高<ItemLink id="vibration_chamber" />（谐振仓）的能源转换效率。

<RecipeFor id="energy_card" />