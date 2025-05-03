---
navigation:
  parent: example-setups/example-setups-index.md
  title: 简单赛特斯石英农场
  icon: certus_quartz_crystal
  position: 110
---

# 简单赛特斯石英农场

如[赛特斯生长机制](../ae2-mechanics/certus-growth.md)所述，自动化<ItemLink id="certus_quartz_crystal" />采集需要<ItemLink id="annihilation_plane" />和<ItemLink id="storage_bus" />的配合。
<ItemLink id="growth_accelerator" />可大幅加速石英芽生长，ME破坏面板则负责收割成熟的<ItemLink id="quartz_cluster" />。利用未成熟芽体掉落<ItemLink id="certus_quartz_dust" />的特性实现精准过滤。

本农场配合<ItemLink id="flawless_budding_quartz" />可实现全自动运行。若使用有瑕、开裂或损坏的母岩，需手动更换（参见[半自动农场](semiauto-certus-farm.md)和[高级农场](advanced-certus-farm.md)实现自动化方案）。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/simple_certus_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="3.7 1 1" max="4 2 2">
        (1) ME破坏面板：无需配置，可附魔时运
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="3.3 2 2">
        (2) 存储总线#1：过滤赛特斯石英水晶
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 .7" max="2 2 1">
        (3) 存储总线#2：过滤赛特斯水晶，优先级高于主存储
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* ME破坏面板 (1) 无需配置，可附魔时运
* 存储总线#1 (2) 过滤<ItemLink id="certus_quartz_crystal" />
* 存储总线#2 (3) 过滤<ItemLink id="certus_quartz_crystal" />，设置[优先级](../ae2-mechanics/import-export-storage.md#storage-priority)高于主存储

## 工作原理

1. ME破坏面板尝试破坏前方方块，因存储总线过滤水晶，仅能破坏<ItemLink id="quartz_cluster" />
2. 存储总线#1将水晶存入容器
3. 存储总线#2让主网络可访问容器中的水晶，高优先级确保水晶优先存入农场容器