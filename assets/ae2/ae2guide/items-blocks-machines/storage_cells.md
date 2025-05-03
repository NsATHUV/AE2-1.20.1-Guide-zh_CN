---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 存储元件
  icon: item_storage_cell_1k
  position: 410
categories:
- tools
item_ids:
- ae2:item_cell_housing
- ae2:fluid_cell_housing
- ae2:cell_component_1k
- ae2:cell_component_4k
- ae2:cell_component_16k
- ae2:cell_component_64k
- ae2:cell_component_256k
- ae2:item_storage_cell_1k
- ae2:item_storage_cell_4k
- ae2:item_storage_cell_16k
- ae2:item_storage_cell_64k
- ae2:item_storage_cell_256k
- ae2:fluid_storage_cell_1k
- ae2:fluid_storage_cell_4k
- ae2:fluid_storage_cell_16k
- ae2:fluid_storage_cell_64k
- ae2:fluid_storage_cell_256k
---

# 存储元件

<Column>
  <Row>
    <ItemImage id="item_storage_cell_1k" scale="4" />

    <ItemImage id="item_storage_cell_4k" scale="4" />

    <ItemImage id="item_storage_cell_16k" scale="4" />

    <ItemImage id="item_storage_cell_64k" scale="4" />

    <ItemImage id="item_storage_cell_256k" scale="4" />
  </Row>

  <Row>
    <ItemImage id="fluid_storage_cell_1k" scale="4" />

    <ItemImage id="fluid_storage_cell_4k" scale="4" />

    <ItemImage id="fluid_storage_cell_16k" scale="4" />

    <ItemImage id="fluid_storage_cell_64k" scale="4" />

    <ItemImage id="fluid_storage_cell_256k" scale="4" />
  </Row>
</Column>

存储元件是应用能源中的核心存储方式，需放入<ItemLink id="drive" />（ME驱动器）或<ItemLink id="chest" />（ME箱子）中使用。

关于存储容量的"字节与类型"机制，详见[字节与类型](../ae2-mechanics/bytes-and-types.md)。

若元件为空，手持时按下Shift+右键可取出存储组件。

## 不同类型数量下的存储容量

由于[类型预占机制](../ae2-mechanics/bytes-and-types.md)，存储1种类型的元件容量是存储63种类型时的约2倍。

| 元件                                    | 单类型存储总容量 | 满类型（63种）存储总容量 |
| -------------------------------------- | --------------: | ----------------------: |
| <ItemLink id="item_storage_cell_1k" /> |           8,128 |                   4,160 |
| <ItemLink id="item_storage_cell_4k" /> |          32,512 |                  16,640 |
| <ItemLink id="item_storage_cell_16k" />|         130,048 |                  66,560 |
| <ItemLink id="item_storage_cell_64k" />|         520,192 |                 266,240 |
| <ItemLink id="item_storage_cell_256k" />|       2,080,768 |               1,064,960 |

## 分区过滤

可通过<ItemLink id="cell_workbench" />（元件工作台）设置过滤规则，类似于<ItemLink id="storage_bus" />（存储总线）的功能。

即使当前未拥有某物品，仍可通过JEI/REI将物品拖入过滤槽（流体需通过容器设置）。

## 升级卡支持

存储元件支持以下[升级卡](upgrade_cards.md)，需在元件工作台中安装：

* <ItemLink id="fuzzy_card" />（流体元件不可用）：支持按耐久度过滤或忽略物品NBT
* <ItemLink id="inverter_card" />：将过滤模式从白名单切换为黑名单
* <ItemLink id="equal_distribution_card" />：为每种类型分配等量存储空间，避免单一类型占满元件
* <ItemLink id="void_card" />：当元件满时销毁多余物品（若使用均分卡则按类型分配空间销毁），防止生产堵塞（需谨慎设置过滤）
* 便携元件可安装<ItemLink id="energy_card" />以提升电池容量

## 染色

便携式物品/流体元件可通过与染料合成来染色，方式类似皮革护甲。

# 元件外壳

存储元件可通过"存储组件+外壳"合成，或直接环绕存储组件制作：

<Row>
  <Recipe id="network/cells/item_storage_cell_1k" />

  <Recipe id="network/cells/item_storage_cell_1k_storage" />
</Row>

单独合成外壳的配方如下：

<Row>
  <RecipeFor id="item_cell_housing" />

  <RecipeFor id="fluid_cell_housing" />
</Row>

# 存储组件

存储组件决定元件的容量等级，每级容量提升4倍且需要3个前级组件合成：

<Column>
  <Row>
    <RecipeFor id="cell_component_1k" />

    <RecipeFor id="cell_component_4k" />

    <RecipeFor id="cell_component_16k" />
  </Row>

  <Row>
    <RecipeFor id="cell_component_64k" />

    <RecipeFor id="cell_component_256k" />
  </Row>
</Column>

# 物品存储元件

物品存储元件最多可存储63种不同类型物品，提供标准容量等级：

<Column>
  <Row>
    <Recipe id="network/cells/item_storage_cell_1k_storage" />

    <Recipe id="network/cells/item_storage_cell_4k_storage" />

    <Recipe id="network/cells/item_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/item_storage_cell_64k_storage" />

    <Recipe id="network/cells/item_storage_cell_256k_storage" />
  </Row>
</Column>

## 便携式物品存储

此类元件相当于随身<ItemLink id="chest" />，可在<ItemLink id="charger" />（充能器）中充电。

与标准元件不同，其类型容量随字节容量增加而减少，且总字节容量减半。

除常规升级卡外，还可安装<ItemLink id="energy_card" />提升电池容量：

<Column>
  <Row>
    <RecipeFor id="portable_item_cell_1k" />

    <RecipeFor id="portable_item_cell_4k" />

    <RecipeFor id="portable_item_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_item_cell_64k" />

    <RecipeFor id="portable_item_cell_256k" />
  </Row>
</Column>

# 流体存储元件

流体存储元件最多可存储5种不同类型流体，提供标准容量等级：

<Column>
  <Row>
    <Recipe id="network/cells/fluid_storage_cell_1k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_4k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/fluid_storage_cell_64k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_256k_storage" />
  </Row>
</Column>

## 便携式流体存储

此类元件相当于随身<ItemLink id="chest" />，可在<ItemLink id="charger" />（充能器）中充电。

与标准元件不同，其类型容量随字节容量增加而减少，且总字节容量减半。

除常规升级卡外，还可安装<ItemLink id="energy_card" />提升电池容量：

<Column>
  <Row>
    <RecipeFor id="portable_fluid_cell_1k" />

    <RecipeFor id="portable_fluid_cell_4k" />

    <RecipeFor id="portable_fluid_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_fluid_cell_64k" />

    <RecipeFor id="portable_fluid_cell_256k" />
  </Row>
</Column>

# 创造物品/流体元件

<Row>
  <ItemImage id="creative_item_cell" scale="2" />

  <ItemImage id="creative_fluid_cell" scale="2" />
</Row>

创造物品/流体元件**不提供无限存储**，而是作为被[分区](cell_workbench.md)物品或流体的无限源与吸收池。