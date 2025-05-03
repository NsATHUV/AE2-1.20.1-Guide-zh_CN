---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME IO端口
  icon: io_port
  position: 210
categories:
- devices
item_ids:
- ae2:io_port
---

# ME IO端口

<BlockImage id="io_port" p:powered="true" scale="8" />

IO端口可用于快速将[存储元件](../items-blocks-machines/storage_cells.md)与[网络存储](../ae2-mechanics/import-export-storage.md)之间进行数据转移。

可使用<ItemLink id="certus_quartz_wrench" />旋转设备方向。

## 设置项

* 可配置当元件为空/已满/操作完成时自动移至输出槽
* 安装<ItemLink id="redstone_card" />后支持红石触发条件设置
* GUI中央箭头可设置传输方向：从元件到网络存储，或反向传输

## 可安装升级

IO端口支持以下[升级卡](upgrade_cards.md)：
* <ItemLink id="speed_card" /> 提升单次操作传输量
* <ItemLink id="redstone_card" /> 添加红石控制（高电平激活/低电平激活/脉冲激活）

## 合成配方

<RecipeFor id="io_port" />