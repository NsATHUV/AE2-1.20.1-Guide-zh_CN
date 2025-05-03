---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 空间IO
  icon: spatial_storage_cell_2
---

# 空间IO

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/spatial_storage_1x1x1.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="2 2 2">
        将要被移动的区域
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />

</GameScene>

空间IO是对世界当中的空间进行剪切和粘贴的一种方法。它可以用于<ItemLink id="flawless_budding_quartz" />的移动，
在你的基地你创建一个可随着需求变化内饰的房间，甚至是移动末地传送门。

它的工作原理是把指定区域与空间存储维度中的等大区域进行**交换**，把空间塔内含有的所有东西都送到空间存储维度中，并将该维度相应位置的东西都送到空间塔的位置。

换言之，如果你能够在维度间穿梭(空间IO**确实可以**用来做传送器，但是过程复杂并且极不稳定，超出了本教程的范围)，你可以将其用作大小可调的紧凑机器或是口袋维度。

# 多方块结构搭建

若要使空间IO工作并选取剪切/粘贴范围，我们需要把各组成部分按照特定的结构搭建起来。

所有组分必须在同一个[网络](me-network-connections.md)中时它们才能正常工作，一个网络中只能建立一个空间IO系统。
因此，建议使用[子网](subnetworks.md)。

## 空间IO端口

<BlockImage id="spatial_io_port" p:powered="true" scale="4" />

<ItemLink id="spatial_io_port" />用于控制空间IO操作。它可以显示空间塔多方块结构的统计数据，并用于存放[空间元件](../items-blocks-machines/spatial_cells.md)。

它会显示
- 网络中已存储的和最大[能量](energy.md)值
- 操作所需的能量。该值可能会很大，并且会被瞬间消耗，请确保你有足够的[能源元件](../items-blocks-machines/energy_cells.md)来应对
- 空间塔的效率
- 选区的大小

要进行空间IO操作，你需要把空间存储元件放进空间IO端口的输入槽，并给端口一个红石脉冲。 
它会把空间塔中的区域与空间存储维度中的区域**交换**。这意味着如果你把一些方块送进空间存储维度后**再将另外一部分方块放置在空间塔的范围内**，
那么在你把元件放回输入槽并再次触发IO端口时，第二组方块会消失，而第一组方块会重新出现。

**要小心，一切位于范围内的实体，也包括你，会被一并交换。如果你没有出去的方法，你就会被困在空间存储维度中，困在一个黑暗的、一成不变的盒子里。**
可以用这个去捉弄你的朋友！

## 空间塔

<BlockImage id="spatial_pylon" p:powered_on="true" scale="4" />

<ItemLink id="spatial_pylon" />是空间IO结构的主体，决定受影响的区域。

受影响的区域由空间塔外侧的边界框决定，实际区域会在各个方向上均收缩1格。

空间塔的构造规则如下：
- 最小3x3x3(选定1x1x1的区域)
- 所有空间塔都必须在边界框区域内
- 所有空间塔都必须位于同一网络内
- 空间塔在各个方向上都必须至少有2格长

例如，假如你需要确定一块3x3x3的区域。根据规则2，所有空间塔必须在一块包裹着你要选择的区域的5x5x5区域的表面层内。
它们的构造几乎是无限制的，只要它们都在表面层内。

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/spatial_storage_3x3x3_pylon_demonstration.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        将要被移动的区域
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

下面是更为合理的构造：

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/better_spatial_storage_3x3x3.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        将要被移动的区域
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 效率

空间塔的效率取决于边界框的填充量。对大区域使用最简单的构造将会很低效，很可能需要**数十亿**AE。

## 元件的尺寸

一旦一个[空间元件](../items-blocks-machines/spatial_cells.md)被使用，它的尺寸就会被完全确定(例如3x4x2)并关联到空间存储维度中的一块区域。
**你无法在空间元件使用后将其重置、重新格式化或改变其尺寸。** 需要不同尺寸的话就需要再做一个元件。

元件的实际尺寸与它的名称无关。16^3的元件的尺寸**至多**是16x16x16。

值得指出的是，这块区域是有向的，无法被旋转。2x2x3的区域和3x2x2的区域不同，尽管它们体积相同。

若元件的尺寸与确定的区域的尺寸(可以在IO端口中查看)不符，IO端口将不会工作。