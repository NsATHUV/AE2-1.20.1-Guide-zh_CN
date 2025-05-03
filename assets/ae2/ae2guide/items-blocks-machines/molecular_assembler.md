---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 分子装配室
  icon: molecular_assembler
  position: 310
categories:
- machines
item_ids:
- ae2:molecular_assembler
---

# 分子装配室

<BlockImage id="molecular_assembler" scale="8" />

分子装配室接收输入物品，并根据相邻<ItemLink id="pattern_provider" />的定义、或插入的<ItemLink id="crafting_pattern" />/<ItemLink id="smithing_table_pattern" />/<ItemLink id="stonecutting_pattern" />执行合成操作，最终将产物推送至相邻容器。

本示例装配室加载了"1个橡木=4个橡木木板"的合成样板。当橡木通过顶部漏斗输入时，装配室将执行合成并通过底部漏斗输出木板。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/standalone_assembler.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 核心功能

分子装配室的主要用途是与<ItemLink id="pattern_provider" />配合使用。此时样板供应器会将合成配方信息与原料一并发送至相邻装配室。由于装配室能自动将合成产物弹出至相邻容器（从而进入样板供应器的返回槽），这种组合即可实现自动化合成。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 可安装升级

分子装配室支持以下升级卡：
* <ItemLink id="speed_card" />（加速卡）

## 合成配方

<RecipeFor id="molecular_assembler" />

## 注意事项

Optifine模组会破坏"产物自动推送"功能，建议使用其他优化模组替代。