---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME控制器
  icon: controller
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:controller
---

# ME控制器

<BlockImage id="controller" p:state="online" scale="8" />

ME控制器是[ME网络](../ae2-mechanics/me-network-connections.md)的核心组件。若网络未配置控制器，则处于"临时网络"状态，最多仅支持8个需[频道](../ae2-mechanics/channels.md)的[设备](../ae2-mechanics/devices.md)。

## 核心功能

* 每个控制器面提供32个[频道](../ae2-mechanics/channels.md)
* 同一ME网络仅允许存在一个控制器多方块结构
* 每个控制器方块需消耗6 AE/刻能量（内置8000 AE存储，大型网络需额外[能源元件](../ae2-mechanics/energy.md)）

## 多方块结构规则

控制器可自由组合构建，但需遵循以下原则：

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controllers.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

1. **完整连接**：所有控制器方块必须相互连接，否则显示红色
2. **尺寸限制**：最大7x7x7体积，超出部分显示红色
3. **轴线限制**：同一轴线最多允许两个相邻方块，违规部分停用变红

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controller_rules.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

当满足所有条件且供电正常时，控制器将呈现彩色循环光效。

## 诊断功能

右键点击可打开与<ItemLink id="network_tool" />相同的网络诊断界面。

## 合成配方

<RecipeFor id="controller" />