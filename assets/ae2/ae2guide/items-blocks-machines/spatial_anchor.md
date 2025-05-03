---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 空间锚
  icon: spatial_anchor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:spatial_anchor
---

# 空间锚

<BlockImage id="spatial_anchor" p:powered="true" scale="8"/>

ME网络需要区块加载才能使其[设备](../ae2-mechanics/devices.md)正常工作。若仅部分网络被加载，可能导致功能异常。空间锚通过强制加载网络覆盖的所有区块解决此问题。单根跨越区块边界的线缆即可触发新区块加载。

空间锚的加载效果可沿[量子桥](quantum_bridge.md)传播，但不可跨维度。若存在跨维度量子桥（如主世界-下界），需在两端网络各部署空间锚。

默认配置下会启用加载区块的随机刻机制，可通过AE2配置文件关闭。

可使用<ItemLink id="certus_quartz_wrench" />旋转设备方向（如有需要）。

## 设置项

* 提供全局能源单位切换（AE/E/FE）
* 可显示加载区块的全息投影

## 能源消耗

空间锚的能源消耗遵循以下公式：

e = 80 + (x*(x+1))/2

其中：
- e = 消耗的能源量（AE）
- x = 加载的区块数量

## 合成配方

<RecipeFor id="spatial_anchor" />