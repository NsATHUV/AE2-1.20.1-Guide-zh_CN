---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 赛特斯石英母岩
  icon: flawless_budding_quartz
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:flawless_budding_quartz
- ae2:flawed_budding_quartz
- ae2:chipped_budding_quartz
- ae2:damaged_budding_quartz
- ae2:small_quartz_bud
- ae2:medium_quartz_bud
- ae2:large_quartz_bud
- ae2:quartz_cluster
---

# 赛特斯石英母岩

（另见[赛特斯生长机制](../ae2-mechanics/certus-growth.md)）

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

类似紫水晶结构，赛特斯石英芽会从母岩上生长。母岩可在[陨石](../ae2-mechanics/meteorites.md)中找到，分为四个等级：无瑕、有瑕、开裂、损坏，可通过HWYLA/Jade/The One Probe等模组或F3界面识别。

有瑕/开裂/损坏的母岩在芽体生长时，每阶段都有几率退化，最终变为普通<ItemLink id="quartz_block" />。

无瑕母岩永不退化，为无限生长源。

普通镐破坏母岩会使其退化一级，精准采集镐破坏则不会退化（无瑕母岩除外）。**这意味着无法用镐直接采集无瑕母岩**，需使用[空间存储](../ae2-mechanics/spatial-io.md)技术移动。

## 合成配方

有瑕/开裂/损坏母岩可通过将前一级母岩（或石英块）与<ItemLink id="charged_certus_quartz_crystal" />投入水中制作。无瑕母岩仅自然生成。

<Row>
  <RecipeFor id="damaged_budding_quartz" />

  <RecipeFor id="chipped_budding_quartz" />

  <RecipeFor id="flawed_budding_quartz" />
</Row>