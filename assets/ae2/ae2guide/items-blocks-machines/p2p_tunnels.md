---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: P2P通道
  icon: me_p2p_tunnel
  position: 210
categories:
- devices
item_ids:
- ae2:me_p2p_tunnel
- ae2:redstone_p2p_tunnel
- ae2:item_p2p_tunnel
- ae2:fluid_p2p_tunnel
- ae2:fe_p2p_tunnel
- ae2:light_p2p_tunnel
---

# 点对点通道

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

P2P通道能在不直接干预网络的情况下传输物品、流体、红石信号、能源、光照和[频道](../ae2-mechanics/channels.md)。每种P2P通道仅传输特定类型内容，本质上是通过网络建立远程两点间的定向传输通道。

![通道示意图](../assets/assemblies/p2p_portal.png)

例如，物品P2P通道连接的漏斗与木桶将建立直接传输链路：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_hopper_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

但相邻的两个木桶不会通过P2P通道自动传输物品：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_barrel_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

红石P2P通道的典型应用场景：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_redstone.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 通道类型与调谐

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="180" pitch="90" />
</GameScene>

不同P2P通道的调谐方式：
- **ME通道**：使用任意[线缆](../items-blocks-machines/cables.md)右键点击
- **红石通道**：使用红石元件调谐
- **物品通道**：使用容器类物品（如箱子）调谐
- **流体通道**：使用流体容器（如桶）调谐
- **能源通道**：使用储能物品（如电池）调谐
- **光通道**：使用光源物品（如火把）调谐

特殊机制：
- ME通道的频道无法穿透其他ME通道
- 能源通道会对传输的FE/E能源征收5%的损耗税

## 核心应用场景

ME通道最常用于[频道](../ae2-mechanics/channels.md)的高密度传输。通过单根致密线缆传输多组频道：

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/p2p_compact_channels.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 1.3 6.3" max="2 2.7 6.7">
        石英纤维实现主网与子网间的能源共享
  </BoxAnnotation>

  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

结合[量子链接仓](quantum_bridge.md)的远距传输方案：

![量子通道示意图](../assets/diagrams/p2p_quantum_network.png)

## 嵌套限制

ME通道不支持递归嵌套传输（红色线缆的ME通道处于离线状态），但其他类型通道可穿透ME通道：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_nesting.snbt" />
  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

## 通道绑定

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_linking_frequency.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

使用<ItemLink id="memory_card" />绑定通道：
- **Shift+右键点击**输入端生成新频率（显示为彩色矩阵）
- **右键点击**输出端完成绑定
- 支持单输入多输出（ME通道的频道将被均分）

## 合成配方

<RecipeFor id="me_p2p_tunnel" />