---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME无线访问点
  icon: wireless_access_point
  position: 210
categories:
- devices
item_ids:
- ae2:wireless_booster
- ae2:wireless_access_point
---

# ME无线访问点

<BlockImage id="wireless_access_point" p:state="has_channel" scale="8" />

允许通过<ItemLink id="wireless_terminal" />（无线终端）进行无线访问。覆盖范围和能耗取决于安装的<ItemLink id="wireless_booster" />（无线信号增幅器）数量。

一个网络中可以存在任意数量的无线访问点，每个访问点可安装多个增幅器，通过调整配置优化能耗和覆盖范围。

需要占用[频道](../ae2-mechanics/channels.md)。

同时用于绑定[无线终端](wireless_terminals.md)。

# 无线信号增幅器

<ItemImage id="wireless_booster" scale="2" />

用于扩展无线访问点的信号覆盖范围。

## 合成配方

<RecipeFor id="wireless_access_point" />

<RecipeFor id="wireless_booster" />