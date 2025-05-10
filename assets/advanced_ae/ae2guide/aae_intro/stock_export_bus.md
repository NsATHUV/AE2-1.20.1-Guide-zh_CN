---
navigation:
  parent: aae_intro/aae_intro-index.md
  title: 存量输出总线
  icon: advanced_ae:stock_export_bus_part
categories:
  - advanced items
item_ids:
  - advanced_ae:stock_export_bus_part
---

# 存量输出总线

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_stock_export_bus.snbt"></ImportStructure>
</GameScene>

该总线可配置为精确导出指定数量的过滤物品堆。通过持续追踪目标容器中的当前物品数量，确保不会超出预设数值。配置方法如下：

1. 打开总线GUI
2. 将需要导出的物品拖拽至过滤槽
3. **中键点击**设置目标数量（支持精确数值输入）

*注意：本总线仅控制输出上限，不会主动移除容器中超出设定数量的物品/流体。当目标容器内物品数量超过设定值时，将暂停导出操作。*

技术特性：
- 支持物品与流体的精准配额控制
- 与ME网络库存实时同步
- 可配合<ItemLink id="ae2:fuzzy_card" />模糊卡使用
- 配置参数持久化存储（区块重载后仍生效）