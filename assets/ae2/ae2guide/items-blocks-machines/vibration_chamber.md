---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 谐振仓
  icon: vibration_chamber
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:vibration_chamber
---

# 谐振仓

<BlockImage id="vibration_chamber" p:active="true" scale="8" />

虽然网络的主要供能方式是<ItemLink id="energy_acceptor" />（能源接收器），但谐振仓可直接生成中小量级的AE能源。

默认配置（无[升级卡](upgrade_cards.md)且使用默认设置）下可产出40 AE/t。

当网络[能源存储](../ae2-mechanics/energy.md)满载时，谐振仓会降低燃料消耗以节能，但无法完全停止工作。

## 设置选项

* 可切换全局能源显示单位（AE或E/FE）

## 升级卡支持

谐振仓支持以下[升级卡](upgrade_cards.md)：

* <ItemLink id="energy_card" />：提升50%能源转换效率（最高+150%，即基础效率的250%）
* <ItemLink id="speed_card" />：增加50%燃烧速率（最高+150%，即基础输出的250%）

## 配置文件参数

可在.minecraft/config/ae2/common.json中调整以下参数：

* `baseEnergyPerFuelTick`：设置基础能源转换效率（未升级状态）
* `minEnergyPerGameTick`：设置最低能源产出（即使网络无需能源也会缓慢消耗燃料）
* `maxEnergyPerGameTick`：设置未升级状态下的最大输出（及工作速度）

## 合成配方

<RecipeFor id="vibration_chamber" />