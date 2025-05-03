---
navigation:
  parent: example-setups/example-setups-index.md
  title: 紫水晶农场
  icon: minecraft:amethyst_shard
---

# 紫水晶自动化种植

虽然<ItemLink id="growth_accelerator" />对紫水晶有效，但传统的[赛特斯石英芽](../items-blocks-machines/budding_certus.md)过滤方案不适用于紫水晶芽。未成熟的紫水晶芽不会掉落任何物品（与掉落<ItemLink id="certus_quartz_dust" />的赛特斯石英芽不同），因此<ItemLink id="annihilation_plane" />会持续破坏它们，因为网络始终可以存储"空物品"。

解决方案是为<ItemLink id="annihilation_plane" />附魔精准采集。这样未成熟的紫水晶芽会掉落其物理芽块的不同阶段形态，从而可以进行过滤。

随后需要通过<ItemLink id="formation_plane" />重新放置<ItemLink id="minecraft:amethyst_cluster" />，再由未附魔的<ItemLink id="annihilation_plane" />二次破坏以获取<ItemLink id="minecraft:amethyst_shard" />。

注意：由于晶簇具有方向性，成型面板对面必须存在实体方块面。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/amethyst_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 1 1" max="3 2 2">
        (1) ME破坏面板#1：无配置界面，需附魔精准采集
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1 1" max="2.3 2 2">
        (2) ME成型面板：过滤设置为紫水晶晶簇
        <ItemImage id="minecraft:amethyst_cluster" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 0.7 1" max="2 1 2">
        (3) ME破坏面板#2：无配置界面，可附魔时运
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 1" max="1.3 1 2">
        (4) 存储总线#1：过滤设置为紫水晶碎片
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 .7" max="1 1 1">
        (5) 存储总线#2：过滤设置为紫水晶碎片，优先级高于主存储
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        连接至主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* 第一个<ItemLink id="annihilation_plane" /> (1) 需附魔精准采集
* <ItemLink id="formation_plane" /> (2) 过滤设置为<ItemLink id="minecraft:amethyst_cluster" />
* 第二个<ItemLink id="annihilation_plane" /> (3) 可附魔时运
* 第一个<ItemLink id="storage_bus" /> (4) 过滤设置为<ItemLink id="minecraft:amethyst_shard" />
* 第二个<ItemLink id="storage_bus" /> (5) 过滤设置为<ItemLink id="minecraft:amethyst_shard" />，[存储优先级](../ae2-mechanics/import-export-storage.md#storage-priority)高于主存储

## 工作原理

1. 第一个<ItemLink id="annihilation_plane" />（附魔精准采集）仅能破坏紫水晶晶簇，因子网存储仅接受晶簇形态
2. <ItemLink id="formation_plane" />将晶簇重新放置到对面方块表面
3. 第二个<ItemLink id="annihilation_plane" />（可附魔时运）破坏成熟晶簇，产出紫水晶碎片
4. 第一个<ItemLink id="storage_bus" />将碎片存入木桶（理论上无需过滤，因第二个破坏面板仅处理成熟晶簇）
5. 第二个<ItemLink id="storage_bus" />以高优先级将碎片接入主网络，确保优先存入农场木桶而非主存储