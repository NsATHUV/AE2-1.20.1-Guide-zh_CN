---
navigation:
  parent: example-setups/example-setups-index.md
  title: 高级赛特斯农场
  icon: certus_quartz_crystal
  position: 120
---

# 高级赛特斯农场

本方案基于[半自动赛特斯农场](semiauto-certus-farm.md)，但完全整合到ME网络系统中。

无需手动维护大量石英母岩库存，本装置通过[充能器自动化](charger-automation.md)和[水中充能自动化](throw-in-water-automation.md)实现全自动运作。

**注意：这是一个复杂的多层结构设计，请旋转视角以全面查看各组件**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/advanced_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) ME破坏面板#1：无配置界面，可附魔时运
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1.7" max="3 3 2">
        (2) 存储总线#1：过滤设置为赛特斯石英水晶
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    晶簇处理子网
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) ME破坏面板#2：无配置界面，需附魔精准采集
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1.7" max="3 2 2">
        (4) 存储总线#2：过滤设置为赛特斯石英块
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    石英块处理子网
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) ME成型面板：保持默认配置
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0.7 2" max="3 1 3">
        (6) 输入总线：过滤设置为有瑕的赛特斯石英母岩
        <BlockImage id="flawed_budding_quartz" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    母岩放置子网
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="1.7 2 2" max="2 3 3">
        (7) 存储总线#3：过滤设置为赛特斯石英水晶，优先级高于主存储
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#aaaadd" min="2 1 2" max="3 2 3">
        (8) ME接口：设置保留1个有瑕的赛特斯石英母岩，安装合成卡
        <Row><BlockImage id="flawed_budding_quartz" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="1.5 0.5 0" color="#00ff00">
        连接至主网络、充能器自动化及水中充能自动化
        <Row>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        </Row>
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## 配置说明

### 晶簇处理子网:
* 第一个<ItemLink id="annihilation_plane" /> (1) 无配置界面，可附魔时运
* 第一个<ItemLink id="storage_bus" /> (2) 过滤设置为<ItemLink id="certus_quartz_crystal" />

### 石英块处理子网:
* 第二个<ItemLink id="annihilation_plane" /> (3) 需附魔精准采集
* 第二个<ItemLink id="storage_bus" /> (4) 过滤设置为<ItemLink id="quartz_block" />

### 母岩放置子网:
* <ItemLink id="formation_plane" /> (5) 保持默认配置
* <ItemLink id="import_bus" /> (6) 过滤设置为<ItemLink id="flawed_budding_quartz" />

### 主网络设置:
* 第三个<ItemLink id="storage_bus" /> (7) 过滤设置为<ItemLink id="certus_quartz_crystal" />，[存储优先级](../ae2-mechanics/import-export-storage.md#storage-priority)高于主存储
* <ItemLink id="interface" /> (8) 设置保留1个<ItemLink id="flawed_budding_quartz" />，安装<ItemLink id="crafting_card" />

## 工作原理

### 晶簇处理子网:
工作逻辑与[基础赛特斯农场](simple-certus-farm.md)类似：
1. <ItemLink id="annihilation_plane" />尝试破坏前方方块，但因子网存储仅接受<ItemLink id="certus_quartz_crystal" />，故仅能破坏<ItemLink id="quartz_cluster" />
2. <ItemLink id="storage_bus" />将水晶存入木桶

### 石英块处理子网:
用于在母岩退化为普通<ItemLink id="quartz_block" />时进行回收：
1. <ItemLink id="annihilation_plane" />需附魔精准采集以避免母岩受损，仅能破坏<ItemLink id="quartz_block" />
2. <ItemLink id="storage_bus" />将石英块送回<ItemLink id="interface" />，供[水中充能自动化](throw-in-water-automation.md)重新生成母岩

### 母岩放置子网:
负责部署新的<ItemLink id="flawed_budding_quartz" />：
1. <ItemLink id="import_bus" />从<ItemLink id="interface" />导入母岩至[网络存储](../ae2-mechanics/import-export-storage.md)
2. <ItemLink id="formation_plane" />将母岩放置到指定位置

### 主网络功能:
* 高优先级<ItemLink id="storage_bus" />确保水晶优先存入农场木桶，供[充能器自动化](charger-automation.md)使用
* <ItemLink id="interface" />通过<ItemLink id="crafting_card" />实现母岩的[自动合成](../ae2-mechanics/autocrafting.md)补给
