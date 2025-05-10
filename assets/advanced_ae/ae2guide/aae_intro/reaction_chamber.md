---
navigation:
  parent: aae_intro/aae_intro-index.md
  title: 反应仓
  icon: advanced_ae:reaction_chamber
categories:
  - advanced devices
item_ids:
  - advanced_ae:reaction_chamber
---

# 反应仓

<BlockImage id="advanced_ae:reaction_chamber" scale="4"></BlockImage>

该设备能够通过使用催化剂流体和大量能源加速化学反应。通过精确控制反应环境，可使自然界中原本缓慢的化学反应在仓室内高效进行。

## 供能方式

反应仓在加速状态下耗电量较大。使用加速卡会提升总能耗速率，同时增加每tick的能源需求。当直接通过ME系统供电时，若单tick所需能量无法满足，可能引发供电波动（ME系统电源反复启停）。建议在AE系统中配置<ItemLink id="ae2:dense_energy_cell" />作为能源缓冲。反应仓也可直接从存储元件中的能源元件（需Applied Flux模组）获取能量进行充能，避免消耗ME系统缓冲能源。若当前发电量不足，可减少加速卡数量。

*注意：线缆形式的样板供应器/接口（附着于线缆的组件）不提供网格连接。如需通过这些设备供能，需额外连接福鲁伊克斯线缆至反应仓。*

## 全方块样板供应器

完整方块形态的样板供应器可将反应仓接入AE2网格，实现按需取能并消除仓内缓冲需求。当电网总能量低于单tick需求时，处理进度将减缓并在界面显示警告。推荐此模式下连接多个<ItemLink id="ae2:dense_energy_cell" />。

## 外部供能

可通过外部电源为反应仓缓冲器充能以启动处理流程。当外部供能速率不足时，仓体界面将显示警告提示。

## 感应卡（需额外模组：Applied Flux）

感应卡可插入线缆式或定向样板供应器，使其能够导出能源元件存储的能量。正确配置后可为反应仓供能。需注意感应卡与部分AE2组件具有启动缓冲时间机制——初始低速运行，随着时间推移逐渐提升速率。这意味着初期可能因能量储备不足无法全速运作，但随着处理持续进行，感应卡将逐步达到最佳供能状态。