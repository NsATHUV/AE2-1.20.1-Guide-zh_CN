---
navigation:
  parent: example-setups/example-setups-index.md
  title: 自动调控型原石生成器
  icon: minecraft:cobblestone
---

# 自动调控型原石生成器

原石生成器的自动化很简单，只需将<ItemLink id="annihilation_plane" />朝向标准原版手动生成器即可。但这样会导致网络被原石填满，因此需要加入调控机制。

由于ME破坏面板的工作方式（类似<ItemLink id="import_bus" />），我们无法直接使用带有<ItemLink id="redstone_card" />的<ItemLink id="level_emitter" />控制<ItemLink id="export_bus" />（因为没有中间存储无法直接连接输入输出）。需要采用更迂回的方式。

<ItemLink id="toggle_bus" />可通过红石信号连接/断开网络部件，但会导致网络重启。解决方案：将其置于[子网](../ae2-mechanics/subnetworks.md)中，仅影响子网重启。

我们可以构建一个由<ItemLink id="annihilation_plane" />和<ItemLink id="storage_bus" />组成的独立[子网](../ae2-mechanics/subnetworks.md)，通过<ItemLink id="interface" />接入主网。触发总线通过<ItemLink id="quartz_fiber" />控制子网电源。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/regulated_cobble_gen.snbt" />

<BoxAnnotation color="#dddddd" min="3 2 2" max="7 2.3 3">
        (1) ME破坏面板：无需配置界面，可附魔效率/耐久降低能耗
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 2 2" max="2.3 3 3">
        (2) 存储总线：保持默认配置
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 2.3 2" max="2.7 2.7 2.3">
        (3) ME触发总线：必须位于子网侧而非主网侧
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 3 2.3" max="2.7 3.3 2.7">
        (4) ME标准发信器：设置为"当数量低于阈值时发信"，配置原石和期望数量
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 3" max="2 3 2">
        (5) ME接口：保持默认配置
  </BoxAnnotation>

<DiamondAnnotation pos="0 2.5 1.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

<DiamondAnnotation pos="5 1.5 3.5" color="#00ff00">
        含水台阶可防止水流扩散导致岩浆凝固为黑曜石
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* <ItemLink id="annihilation_plane" /> (1) 无配置界面，可附魔效率/耐久降低能耗
* <ItemLink id="storage_bus" /> (2) 保持默认配置
* <ItemLink id="toggle_bus" /> (3) 必须位于石英纤维连接的子网侧，否则会引发主网重启
* <ItemLink id="level_emitter" /> (4) 设置为"当数量低于阈值时发信"，配置目标物品和数量
* <ItemLink id="interface" /> (5) 保持默认配置

## 工作原理

1. 原石生成器产生原石
2. ME破坏面板破坏原石
3. 存储总线通过ME接口将原石存入主网络
4. 当主网络中原石数量超过设定值时，ME标准发信器停止信号
5. 子网络的能量供给被切断，从而关闭了破坏面板