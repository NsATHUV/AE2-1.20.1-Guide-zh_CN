---
navigation:
  parent: example-setups/example-setups-index.md
  title: 存储元件快速存取器
  icon: io_port
---

# 存储元件快速存取器

如何实现存储元件与箱子/抽屉阵列/背包之间的快速转移？答案是通过<ItemLink id="io_port" />构建子网进行定向传输。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/cell_dumper_filler.snbt" />

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 1">
        (1) ME IO端口：通过界面中央箭头按钮切换"导入网络"或"导出元件"模式，安装3张加速卡
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0.7 0" max="1 1 1">
        (2) 存储总线：保持默认配置
  </BoxAnnotation>

<BoxAnnotation color="#33dd33" min="0 1 0" max="1 2 1">
        此处放置目标容器（箱子/抽屉等）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0.35 0.35" max="2.3 0.65 0.65">
        石英纤维：仅当使用其他网络供能时需要
  </BoxAnnotation>

<DiamondAnnotation pos="3 0.5 0.5" color="#00ff00">
        连接能源（其他网络或能源接收器）
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* <ItemLink id="io_port" /> (1) 通过界面中央箭头按钮切换"导入网络"或"导出元件"模式，安装3张<ItemLink id="speed_card" />实现极速传输
* <ItemLink id="storage_bus" /> (2) 保持默认配置

## 工作原理

### "导入网络"模式

1. <ItemLink id="io_port" />将存储元件内容导入[网络存储](../ae2-mechanics/import-export-storage.md)
2. 子网中唯一的存储端<ItemLink id="storage_bus" />将物品/流体传输至目标容器
* <ItemLink id="energy_cell" />提供充足[能源缓冲](../ae2-mechanics/energy.md)，防止高频传输导致网络断电

### "导出元件"模式

1. <ItemLink id="io_port" />将[网络存储](../ae2-mechanics/import-export-storage.md)内容导出至存储元件
2. 子网中唯一的存储端<ItemLink id="storage_bus" />从目标容器提取物品/流体
* <ItemLink id="energy_cell" />提供充足[能源缓冲](../ae2-mechanics/energy.md)，确保高速传输稳定性