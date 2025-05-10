---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME标签存储总线
    icon: expatternprovider:tag_storage_bus
categories:
- extended devices
item_ids:
- expatternprovider:tag_storage_bus
---

# ME标签存储总线

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_tag_storage_bus.snbt"></ImportStructure>
</GameScene>

ME标签存储总线是<ItemLink id="ae2:storage_bus" />的增强版本，具备以下特性：
- 支持通过物品/流体标签进行精准过滤
- 兼容基础逻辑运算符（& | ^）构建复杂规则
- 支持通配符(*)实现模糊匹配

## 过滤规则示例

- 仅接受原始矿石：
forge:raw_materials/*


- 接受所有锭与宝石：
forge:ingots/* | forge:gems/*


## 逻辑运算符说明
1. **&** 逻辑与：同时满足多个标签（如`forge:plates & thermal:lead`）
2. **|** 逻辑或：满足任意标签即可（如`minecraft:wool | #forge:glass`）
3. **^** 逻辑异或：满足且仅满足一个标签（如`#forge:gems ^ #forge:ingots`）
4. **()** 优先级控制：`(a | b) & c`