---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 赛特斯石英培养
  icon: quartz_cluster
---

# 赛特斯石英培养

## 从新手上路页面Ctrl+C然后Ctrl+V到这儿来的内容

<GameScene zoom="6" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_1.snbt" />
</GameScene>

赛特斯石英芽会从[赛特斯石英母岩](items-blocks-machines/budding_certus.md)中长出来，就像紫水晶一样。
如果你破坏未完成生长的赛特斯石英芽，它会掉落1个<ItemLink id="certus_quartz_dust" />，不受时运附魔影响。
如果你破坏生长完成的赛特斯石英簇，它会掉落4个<ItemLink id="certus_quartz_crystal" />，并且时运附魔会提升这一数目。

赛特斯石英母岩有4种等级：无瑕、有瑕、开裂和损坏。

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_blocks.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

每当石英芽生长至下一阶段，母岩均有可能降级1级，直至变成普通的赛特斯石英块。可将母岩（或石英块）和至少一个<ItemLink id="charged_certus_quartz_crystal" />
一同丢入水中以修复它们（或产生新的母岩）。

<RecipeFor id="damaged_budding_quartz" />

**Throw in: 扔入**

无瑕的赛特斯石英母岩不会降级，能够无限产生赛特斯石英。但是它们无法被合成，也无法被稿子挖掘后移动（会降级），哪怕稿子附魔有精准采集。
（然而，它们**可以**用[空间IO](ae2-mechanics/spatial-io.md)移动）

>译者注：IO = **I**nput & **O**utput, 输入输出。

赛特斯石英芽的自行生长很慢。幸运的是，<ItemLink id="growth_accelerator" />可以大幅加快其相邻母岩上的水晶芽的生长速度。你应当把建造该装置作为你的首要任务。

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_2.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

如果你没有足够的水晶来制作<ItemLink id="energy_acceptor" />或<ItemLink id="vibration_chamber" />，
你可以制作一个<ItemLink id="crank" />并把它放置在你的催生器的一侧。

自动化收获赛特斯石英的方法[参见此处](example-setups/simple-certus-farm.md)。

> 译者注：其实不完全是从新手上路页面复制的。第一个结构的缩放参数(`zoom`)从4改成6了。