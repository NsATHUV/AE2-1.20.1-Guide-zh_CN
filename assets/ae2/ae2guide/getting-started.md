---
navigation:
  title: 新手上路（1.20+）
  position: 10
---

<div class="notification is-info">
  下面的内容仅适用于Minecraft 1.20或更高版本的AE2。
</div>

# 新手上路
## 获取初始材料

<GameScene zoom="4" background="transparent">
  <ImportStructure src="assets/assemblies/meteor_interior.snbt" />
</GameScene>

要开启AE2之旅，你首先要找到[陨石](ae2-mechanics/meteorites.md)。它们很常见并且一般会留下一个大洞，因此你很有可能已经碰见过它们了。
如果你还没有碰见过，那么你需要合成一个<ItemLink id="meteorite_compass" />，它会指向最近的<ItemLink id="mysterious_cube" />。

当你找到陨石后，挖到它的中心。你会找到赛特斯石英簇、赛特斯石英芽、不同种类的[赛特斯石英母岩](items-blocks-machines/budding_certus.md)、以及位于中央的神秘方块。

挖掉你找到的赛特斯石英簇和赛特斯石英块。你也可以挖掘赛特斯石英母岩，但是在没有精准采集附魔的情况下挖掘它们会使其降低1个等级。

不要挖掘无瑕的赛特斯石英母岩，因为即使有精准采集附魔挖掘它们也会使其变成有瑕的，且无法复原。

此外，挖掉陨石中央的神秘方块以获取全部4种压印板。

## 培养赛特斯石英

<GameScene zoom="4" background="transparent">
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


赛特斯石英芽的自行生长很慢。幸运的是，<ItemLink id="growth_accelerator" />可以大幅加快其相邻母岩上的水晶芽的生长速度。你应当把建造该装置作为你的首要任务。

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_2.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

如果你没有足够的水晶来制作<ItemLink id="energy_acceptor" />或<ItemLink id="vibration_chamber" />，
你可以制作一个<ItemLink id="crank" />并把它放置在你的催生器的一侧。

自动化收获赛特斯石英的方法[参见此处](example-setups/simple-certus-farm.md)。

## 对福鲁伊克斯水晶的简单介绍

福鲁伊克斯水晶是你所需要的另一种材料，你应该已经在制作晶体催生器时使用过它。它可通过将充能赛特斯石英、红石和下界石英一同扔入水中来合成。
对此的自动化**留给读者作为练习。**

如果你还不知道的话，顺带一提，<ItemLink id="charger" />是制作<ItemLink id="charged_certus_quartz_crystal" />所必须的。

## 压印处理器

在你搜刮陨石的资源时，你会在破坏神秘方块时得到4块**压印板**。它们被用于<ItemLink id="inscriber" />以制作三种处理器。

<ItemGrid>
  <ItemIcon id="silicon_press" />

  <ItemIcon id="logic_processor_press" />

  <ItemIcon id="calculation_processor_press" />

  <ItemIcon id="engineering_processor_press" />
</ItemGrid>

压印器如同原版的熔炉一样，是有方向性的。从上/下方的物品输入会把物品放入上/下方的物品槽，而从侧面和后方的输入会将物品放入中间的物品槽。 
产物可从侧面或后方输出。

为利用漏斗实现自动化（并减少管道的使用），压印器可以用<ItemLink id="certus_quartz_wrench" />旋转。

每种处理器都制作一些，为下一步制作基础ME系统做准备。处理器生产自动化**留给读者作为练习。**

## 物质能量技术：ME网络与储存

### ME储存是什么？

它读作Emm-Eee(\[emi:\])，意为物质能量(Matter Energy)。

ME是AE2的主要组成部分，它可以说是多方块箱子的一种疯狂科学版，可以为你的储存带来革命性的变化。
ME与Minecraft中的其他储存系统有极大的不同，并且你可能需要另辟蹊径地思考来习惯它；
但是一旦你着手于此，小空间大储存以及多个访问终端仅仅是它能做到的事的冰山一角。

### 开始前要了解的

首先，ME把物品存储在另一种物品中，这些物品叫做[存储元件](items-blocks-machines/storage_cells.md)；它们有5个等级，容量逐级递增。
要使用存储单元，它们必须被放进<ItemLink id="chest" />或<ItemLink id="drive" />中。

<ItemLink id="chest" />能在存储元件被放入后立即显示其内容物，并且你能够像使用<ItemLink id="minecraft:chest" />一样放入或拿出物品，
尽管物品实际被存储在元件而非<ItemLink id="chest" />本身当中。

尽管<ItemLink id="chest" />是理解ME概念的绝佳手段，要真正利用ME的优势，你需要搭建一个[ME网络](ae2-mechanics/me-network-connections.md).

## 第一个ME系统

既然你已经有了AE2里所有的基本材料与机器，你就可以建立起你的第一个ME系统了。它很基本，没有自动合成，没有物流，只有简单、整洁、可搜索的存储。

<GameScene zoom="6" interactive={true}>
<ImportStructure src="assets/assemblies/tiny_me_system.snbt" />

</GameScene>

*   所需材料列表：
    * 1x <ItemLink id="drive" />
    * 1x <ItemLink id="terminal" />或<ItemLink id="crafting_terminal" />
    * 1x <ItemLink id="energy_acceptor" />
    * 一些[线缆](items-blocks-machines/cables.md)，玻璃的、包层的和智能的都行，但是不能用致密的
    * 一些[存储元件](items-blocks-machines/storage_cells.md)，推荐4k版以取得容量与种类的平衡（用4k和1k的组合进行[分区](items-blocks-machines/cell_workbench.md)效率更高，但是太复杂，在此不深入讨论）

---

1.  放置驱动器。
2.  能源接收器（以及一部分其他的AE2[设备](ae2-mechanics/devices.md)）有2种模式——方块式与薄板式，它们可通过工作台相互转化。如果你的能源接收器是方块式的，把它放在驱动器旁；如果它是薄板式的，在驱动器上放置一根线缆并把它放上去。
3.  用你最爱的能源模组产生能源，并用线缆/管道/导管将其导入能源接收器。
4.  在驱动器顶端（或者，与视线平齐处）放置一根线缆然后把你的（合成）终端放上去。
5.  把存储元件放入驱动器中。
6.  享受它带来的便利！
7.  调整一下终端设置。
8.  尽情享受你**无尽**的力量与能力。
9.  最终意识到：宏观上来讲，这网络其实很小。

### 扩展你的网络

现在你有了基础的存储以及对它的访问方法，这是个不错的开端，但你很可能已经在盘算着些什么，也许是自动化？

这方面的一个绝佳实例是在熔炉顶端放一个<ItemLink id="export_bus" />来输入矿石，
并在底端放一个<ItemLink id="import_bus" />来提取烧炼产物。

<ItemLink id="export_bus" />让你能够从网络中把物品提取出来并放进它所依附的容器内，
<ItemLink id="import_bus" />则反过来把物品从它所依附的容器中提取出来输入网络当中。

### 克服限制

现在你大概已经有了将近8台[设备](ae2-mechanics/devices.md)，当这个数字达到9，你就需要管理[频道](ae2-mechanics/channels.md)了，
许多设备（但不是全部）需要占用频道以工作。

一个网络默认支持8个频道，一旦你超过该值，你就需要往网络中添加<ItemLink id="controller" />，它能够极大地扩展你的网络。
[智能线缆](items-blocks-machines/cables.md)能让你看到频道在网络中的路由情况。如果你希望学习频道在网络中的路由机制，你应当大量使用它们。
当然如果你只是有很多红石和荧石，这样干也不是不行。
