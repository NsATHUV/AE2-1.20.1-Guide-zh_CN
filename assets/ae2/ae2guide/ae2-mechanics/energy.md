---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 能量
  icon: energy_cell
---

# 能量

网络需要能量才可以运行。网络带有能量缓冲区，[设备](../ae2-mechanics/devices.md)直接从中获取能量，而
<ItemLink id="vibration_chamber" />和<ItemLink id="energy_acceptor" />(以及<ItemLink id="controller" />)将能量输入进去。
使用<ItemLink id="network_tool" />右键网络中任意元件或是直接右键网络的控制器(如果有)可查看该网络的能量统计信息。
全网范围内的存储与分配意味着能量传输速率是不受限制的，因此设备可获取任意多的能量而能源接收器可以以任意高的速度接收能量，这只受限于你的能量储存区大小。

## Energy Accepting

<Row>
  <BlockImage id="energy_acceptor" scale="4" />

  <GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
  </GameScene>

  <BlockImage id="controller" p:state="online" scale="4" />

  <BlockImage id="vibration_chamber" p:active="true" scale="4" />
  
  <BlockImage id="crystal_resonance_generator" scale="4" />
</Row>

AE2内部并不直接使用Forge能量(Forge端)或是TechReborn能量(Fabric端)，它将这些能量转化为自己的AE能量。这种转化是单向的。
使用<ItemLink id="energy_acceptor" />或<ItemLink id="controller" />可进行此转化，不过控制器的表面最好还是用于获取更多[频道](../ae2-mechanics/channels.md)。
也可以使用<ItemLink id="vibration_chamber" />或通过<ItemLink id="crystal_resonance_generator" />的被动生成来获取，但是AE2的设计就是要和其他产能上做的更好的科技模组合用的。

这一切都在说明一件事：在布设你基地的能源分配系统时，把AE2视为一个简单的多方块机器就好了。

两种能量与AE间转化比率是：

*   2 FE = 1 AE (Forge)
*   1 E  = 2 AE (Fabric)

## 能量存储

<Row>
  <BlockImage id="energy_cell" scale="4" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="4" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="4" />
</Row>

显然，网络每游戏刻可以消耗或获取的能量无法超过它的储存量。
如果一个网络只能存储800AE，当其[设备](../ae2-mechanics/devices.md)需要能量时，它们只能使用至多800AE(假定储存已满)，
而能源接收器也只能存储至多800AE(假定存储为空)。

这是许多奇怪行为的诱因。例如一名玩家搭建了一个只有能源接收器、驱动器、终端以及一些其他设备的小网络，然后想把一物品栏的物品都丢进网络中。
把这些圆石在1游戏刻内都放入网络中所需要的能量超过了该网络所存储的量，因此圆石不会全部进入网络，网络的能量会耗尽并因此重启一次。

**加入能源元件可以解决这一问题**

每一线缆、机器和线缆组分均会为网络提供25AE的能量缓冲区。

<ItemLink id="controller" />内置8,000AE的小能量缓冲区。

<ItemLink id="energy_cell" />可以存储200kAE，只需一个即可应对绝大多数情形，轻松应对日常使用中的能量消耗高峰。

<ItemLink id="dense_energy_cell" />可以存储1.6MAE，一般用于给脱网靠自身能量存储运行的网络供能或是应对[空间存储](spatial-io.md)的瞬时耗能高峰。

<ItemLink id="creative_energy_cell" />是创造专用的测试用元件，提供无尽的抛瓦。

- 此处内容来源于[nhdsd](https://github.com/nhdsd/AE2-Chinese-Guidebook)，由[NsATHUV](https://github.com/NsATHUV)修正。
