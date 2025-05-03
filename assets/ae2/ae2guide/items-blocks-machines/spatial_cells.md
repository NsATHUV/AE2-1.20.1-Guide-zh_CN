---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 空间存储元件
  icon: spatial_storage_cell_128
  position: 410
categories:
- tools
item_ids:
- ae2:spatial_storage_cell_2
- ae2:spatial_storage_cell_16
- ae2:spatial_storage_cell_128
- ae2:spatial_cell_component_2
- ae2:spatial_cell_component_16
- ae2:spatial_cell_component_128
---

# 空间存储元件

<Row>
    <ItemImage id="spatial_storage_cell_2" scale="4" />
    <ItemImage id="spatial_storage_cell_16" scale="4" />
    <ItemImage id="spatial_storage_cell_128" scale="4" />
</Row>

空间存储元件用于[存储物理空间区域](../ae2-mechanics/spatial-io.md)，需在<ItemLink id="spatial_io_port" />（空间IO端口）中使用。

与普通[存储元件](../items-blocks-machines/storage_cells.md)不同，空间存储元件**无法重新格式化**。

**特别注意：空间存储元件一经使用，其尺寸将永久固定，无法重置、重设或调整大小！** 如需不同尺寸，请制作新元件。

## 合成配方

<Row>
    <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />
    <Recipe id="network/cells/spatial_storage_cell_16_cubed_storage" />
    <Recipe id="network/cells/spatial_storage_cell_128_cubed_storage" />
</Row>

# 元件外壳

空间存储元件可通过"空间组件+外壳"或"外壳包裹组件"两种方式合成：

<Row>
    <Recipe id="network/cells/spatial_storage_cell_2_cubed" />
    <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />
</Row>

单独合成元件外壳配方：

<RecipeFor id="item_cell_housing" />

# 空间组件

空间组件是空间存储元件的核心部件，每级组件的存储维度提升8倍：

<Row>
    <RecipeFor id="spatial_cell_component_2" />
    <RecipeFor id="spatial_cell_component_16" />
    <RecipeFor id="spatial_cell_component_128" />
</Row>
