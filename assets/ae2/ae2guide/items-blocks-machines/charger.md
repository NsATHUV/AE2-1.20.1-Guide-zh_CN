---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 充能器
  icon: charger
  position: 310
categories:
- machines
item_ids:
- ae2:charger
---

# 充能器

<BlockImage id="charger" scale="8" />

核心功能：
- 为兼容工具充能
- 将<ItemLink id="certus_quartz_crystal" />转化为<ItemLink id="charged_certus_quartz_crystal" />

## 技术参数

* 能量接口：顶部/底部（支持AE2线缆或FE能源导管）
* 兼容能源：AE2能源（AE）或Forge Energy（FE）
* 物品存取：任意面（仅允许取出成品，无需过滤）
* 方向调整：使用<ItemLink id="certus_quartz_wrench" />旋转设备朝向

## 主要用途

* 制作充能水晶：<ItemLink id="certus_quartz_crystal" /> → <ItemLink id="charged_certus_quartz_crystal" />
* 制作陨石罗盘：<ItemLink id="minecraft:compass" /> → <ItemLink id="meteorite_compass" />
* 村民职业工作站

## 手动充能

在顶部/底部安装<ItemLink id="crank" />，右键转动曲柄直至物品完成充能。

## 简易自动化示例

通过调整朝向实现半自动化供料：

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/charger_hopper.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 合成配方

<RecipeFor id="charger" />