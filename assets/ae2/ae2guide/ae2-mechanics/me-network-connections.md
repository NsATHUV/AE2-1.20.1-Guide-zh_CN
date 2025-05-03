---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 网络连接
  icon: fluix_glass_cable
---

# 网络连接

## “网络”是什么？

“网络”是一组由[线缆](../items-blocks-machines/cables.md)和占据完整方块的机器与[设备](../ae2-mechanics/devices.md)(<ItemLink id="charger" />、<ItemLink id="interface" />、<ItemLink id="drive" />等)等可传输[频道](../ae2-mechanics/channels.md)的方块连接起来的一组[设备](../ae2-mechanics/devices.md)。
技术上一个孤立的线缆也是一个网络，真的。

## 对设备位置的简要介绍

对于有特定网络功能的[设备](../ae2-mechanics/devices.md)
(例如将物品送入或送出[网络存储](../ae2-mechanics/import-export-storage.md)中的<ItemLink id="interface" />、
读取网络中内容的<ItemLink id="level_emitter" />和用作网络存储的<ItemLink id="drive" />等)，
其物理意义上的位置并不重要。

再强调一下，**设备物理意义上的位置并不重要**。重要的只有设备是否联网(以及连入了哪个网络)。 

## 网络连接

使用<ItemLink id="network_tool" />是判断有哪些设备连接到了网络中的简单方法。它会显示网络中的所有组分，
因此如果你看到了不该看到的或是没看到该看到的组分，该网络就有问题。

例如，这是两个独立的网络：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络1
  </BoxAnnotation>

<BoxAnnotation color="#915dcd" min="2 0 0" max="3 2 2">
        网络2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

这也是两个网络，因为<ItemLink id="quartz_fiber" />只共享[能量](../ae2-mechanics/energy.md)而不会使网络相连。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        网络1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="1.3 0 0" max="3 2 2">
        网络2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

然而，这是一个网络。[量子桥](../items-blocks-machines/quantum_bridge.md)就像无线的[致密线缆](../items-blocks-machines/cables.md#dense-cable)一样，
因此两端均为同一网络：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        整体为1个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

这也是一个网络，因为[线缆](../items-blocks-machines/cables.md)的颜色与网络连接无关，只是不同色的线缆不会相连。所有线缆均会与福鲁伊克斯色(无色)线缆相连：
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        整体为1个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 更反直觉的连接方式

在下方的例子是一个网络，因为<ItemLink id="pattern_provider" />作为占据完整方块的设备将具有线缆的功能，且<ItemLink id="inscriber" />类似。
因此，网络连接会通过供应器和压印器。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        整体为1个网络
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

为避免此情况(以使用[子网](../ae2-mechanics/subnetworks.md)来进行自动合成),
可用<ItemLink id="certus_quartz_wrench" />右键供应器使其有方向性，这时它不会传递频道。

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="2 2 2">
        网络1
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="2 0 0" max="4 2 2">
        网络2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 .3 .3" max="1.3 .7 .7">
        注意看线缆为何没有连接在一起
  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

其他没有提供有向网络连接的基本上是[线缆组分](../ae2-mechanics/cable-subparts.md)[设备](../ae2-mechanics/devices.md)，
例如<ItemLink id="import_bus" />、<ItemLink id="storage_bus" />和<ItemLink id="cable_interface" />。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>