---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 赛特斯石英生长机制
  icon: quartz_cluster
---

# 赛特斯石英生长机制

## 基础生长原理

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/budding_certus_1.snbt" />
</GameScene>

赛特斯石英芽会从[石英母岩](../items-blocks-machines/budding_certus.md)上生长，类似紫水晶机制：
- 破坏未成熟石英芽：固定掉落1个<ItemLink id="certus_quartz_dust" />（不受时运影响）
- 破坏成熟石英簇：掉落4个<ItemLink id="certus_quartz_crystal" />（时运附魔可增加数量）

## 母岩品质分级

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

石英母岩分为四个品质等级：
1. 无瑕（Flawless）
2. 有瑕（Flawed）
3. 开裂（Chipped）
4. 损坏（Damaged）

### 退化与修复机制
- 每次石英芽生长阶段提升时，母岩有概率降低品质等级
- 最终退化为普通赛特斯石英块
- 修复方法：将母岩或普通石英块与<ItemLink id="charged_certus_quartz_crystal" />投入水中

<RecipeFor id="damaged_budding_quartz" />

**特殊说明**：  
无瑕母岩不会退化且可持续生产，但无法通过精准采集获取（需使用[空间存储技术](../ae2-mechanics/spatial-io.md)移动）

## 加速生长方案

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_certus_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

- **晶体催生器**（<ItemLink id="growth_accelerator" />）：  
  相邻放置可大幅加速生长（优先建造）

- **能源不足时的替代方案**：  
  安装<ItemLink id="crank" />（木质曲柄）手动充能

## 自动化采集

完整自动化方案请参考：[基础赛特斯农场搭建指南](../example-setups/simple-certus-farm.md)