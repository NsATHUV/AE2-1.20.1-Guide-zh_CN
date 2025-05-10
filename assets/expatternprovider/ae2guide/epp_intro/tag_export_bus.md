---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME标签输出总线
    icon: expatternprovider:tag_export_bus
categories:
- extended devices
item_ids:
- expatternprovider:tag_export_bus
---

# ME标签输出总线

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_tag_export_bus.snbt"></ImportStructure>
</GameScene>

ME标签输出总线是<ItemLink id="ae2:export_bus" />的增强版本，具备以下特性：

- 支持通过物品/流体标签进行精准过滤
- 过滤规则与<ItemLink id="expatternprovider:tag_storage_bus" />完全一致
- 可搭配逻辑运算符（& | ^）构建复杂过滤条件
- 支持通配符(*)实现模糊匹配

## 操作指南
1. 在过滤栏输入标签表达式（如"forge:ingots* & !minecraft:iron_ingot"）
2. 选择白名单/黑名单模式
3. 配置红石信号控制逻辑
4. 安装速度升级卡可提升传输效率

![标签过滤示例](../pic/tag_filter_demo.png)