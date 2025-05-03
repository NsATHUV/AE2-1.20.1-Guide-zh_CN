---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 伪装板
  icon: facade
  icon_nbt: '{item: "minecraft:stone"}'
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:facade
---

# 伪装板

伪装板可用于让基地看起来更整洁。它们能覆盖线缆的各个面，并支持使用多种方块的材质进行伪装。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/facades_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

它们可以覆盖线缆的所有面，但允许[子部件](../ae2-mechanics/cable-subparts.md)和线缆连接点穿透显示。

<GameScene zoom="6"  interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

巧妙运用伪装板可以提升基地的美观度，或制作具有不同面材质的特殊方块。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_3.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 隐藏伪装板

手持<a href="network_tool.md">网络工具</a>时，伪装板将被隐藏。

此时可以直接与伪装板后方的方块交互，无需先行移除伪装板。

## 合成配方

在4个<ItemLink id="cable_anchor" />（线缆锚）中间放置需要伪装的方块。
（**下面只是一张图片，鼠标指上去看不到名字很正常，别奇怪哦！**）

![伪装板合成配方](../assets/diagrams/facade_recipe.png)