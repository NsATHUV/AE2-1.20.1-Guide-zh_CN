---
navigation:
  parent: example-setups/example-setups-index.md
  title: 半自动赛特斯石英农场
  icon: certus_quartz_crystal
  position: 115
---

# 半自动赛特斯石英农场

遗憾的是，[简单石英农场](simple-certus-farm.md)需要<ItemLink id="flawless_budding_quartz" />才能全自动运行。这需要[空间IO](../ae2-mechanics/spatial-io.md)技术或在[陨石](../ae2-mechanics/meteorites.md)上建造农场。

不过AE2具备方块放置与破坏能力，可以实现*自动替换石英母岩*（需定期向输入容器添加<ItemLink id="flawed_budding_quartz" />，并从废料容器取出<ItemLink id="quartz_block" />）

全自动方案请参考[高级赛特斯石英农场](advanced-certus-farm.md)。

本农场整合了三个独立系统，比[简单农场](simple-certus-farm.md)更复杂。

**此建筑结构存在部件遮挡，请旋转视角查看全貌**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/semiauto_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) ME破坏面板#1：无需配置，可附魔时运
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1" max="2.3 3 2">
        (2) 存储总线#1：过滤赛特斯石英水晶
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    晶簇破坏子网
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) ME破坏面板#2：无需配置，需附魔精准采集
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1" max="2.3 2 2">
        (4) 存储总线#2：过滤赛特斯石英块
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    石英块拆除子网
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) ME成型面板：保持默认配置
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0 1" max="2.3 1 2">
        (6) ME输入总线：保持默认配置
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    母岩放置子网
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="0.7 2 1" max="1 3 2">
        (7) 存储总线#3：过滤赛特斯水晶，优先级高于主存储
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

    <DiamondAnnotation pos="1.5 0.5 1.5" color="#00ff00">
        手动添加有瑕母岩
        <BlockImage id="flawed_budding_quartz" scale="2" />
    </DiamondAnnotation>

    <DiamondAnnotation pos="1.5 1.5 1.5" color="#00ff00">
        手动取出石英块
        <BlockImage id="quartz_block" scale="2" />
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## 配置说明

### 晶簇破坏子网

* ME破坏面板#1 (1) 无需配置，可附魔时运
* 存储总线#1 (2) 过滤<ItemLink id="certus_quartz_crystal" />

### 石英块拆除子网

* ME破坏面板#2 (3) 必须附魔精准采集
* 存储总线#2 (4) 过滤<ItemLink id="quartz_block" />

### 母岩放置子网

* ME成型面板 (5) 保持默认配置
* ME输入总线 (6) 保持默认配置

### 主网络设置

* 存储总线#3 (7) 过滤<ItemLink id="certus_quartz_crystal" />，设置[优先级](../ae2-mechanics/import-export-storage.md#storage-priority)高于主存储

## 工作原理

### 晶簇破坏子网

该子网与[简单农场](simple-certus-farm.md)原理类似：

1. ME破坏面板尝试破坏前方方块，因存储总线过滤水晶，仅能破坏<ItemLink id="quartz_cluster" />
2. 存储总线将水晶存入容器

### 石英块拆除子网

当母岩退化为普通石英块时进行拆除：

1. ME破坏面板需附魔精准采集，防止母岩受损，仅能破坏<ItemLink id="quartz_block" />
2. 存储总线将石英块存入废料容器，需手动配合<ItemLink id="charged_certus_quartz_crystal" />在水中修复

### 母岩放置子网

当旧母岩被拆除后自动补充：

1. ME输入总线从输入容器获取新母岩
2. ME成型面板放置母岩

### 主网络设置

* 存储总线#3让主网络（及[充能自动化](charger-automation.md)）可访问水晶容器，高优先级确保水晶优先存入农场容器