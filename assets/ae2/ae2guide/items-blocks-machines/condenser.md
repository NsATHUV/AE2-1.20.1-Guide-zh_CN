---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 物质聚合器
  icon: condenser
  position: 310
categories:
- machines
item_ids:
- ae2:condenser
---

# 物质聚合器

<BlockImage id="condenser" scale="8" />

物质聚合器具备双重功能：
- 作为高效垃圾桶使用
- 生产<ItemLink id="matter_ball" />和[奇点](../items-blocks-machines/singularities.md)
支持处理所有可存入存储元件的物品/流体等

## 工作模式配置

### 垃圾桶模式
直接销毁所有输入物品

### 物质球模式
* 需在顶部插槽放置存储组件（如<ItemLink id="cell_component_1k" />）
* 每256个物品/桶流体合成1个物质球
* 推荐使用1k存储组件（8192字节容量）

### 物质奇点模式
* 需在顶部插槽放置存储组件（如<ItemLink id="cell_component_64k" />）
* 每256,000个物品/桶流体合成1个奇点
* 推荐使用64k存储组件（524,288字节容量）

## 合成配方

<RecipeFor id="condenser" />