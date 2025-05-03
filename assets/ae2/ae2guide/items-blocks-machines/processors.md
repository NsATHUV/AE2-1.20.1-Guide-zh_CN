---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 处理器
  icon: logic_processor
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:logic_processor
- ae2:calculation_processor
- ae2:engineering_processor
- ae2:printed_silicon
- ae2:printed_logic_processor
- ae2:printed_calculation_processor
- ae2:printed_engineering_processor
- ae2:silicon
---

# 处理器系统

<Row>
  <ItemImage id="logic_processor" scale="4" />

  <ItemImage id="calculation_processor" scale="4" />

  <ItemImage id="engineering_processor" scale="4" />
</Row>

处理器是AE2[设备](../ae2-mechanics/devices.md)和机器的核心组件，也是首个重要的自动化挑战。共有三种类型，分别使用金锭、<ItemLink id="certus_quartz_crystal" />和钻石制造。需通过[压印模板](presses.md)在<ItemLink id="inscriber" />中经过多步骤工艺完成（通常需要一系列压印器和过滤管道协同工作）。

## 生产工艺流程

<Column gap="5">
  1. **收集基础材料**：硅、红石、金锭、赛特斯石英水晶、钻石

  <RecipeFor id="silicon" />

  <br />

  2. **预制印刷电路组件**

  <Row>
    <RecipeFor id="printed_silicon" />

    <RecipeFor id="printed_logic_processor" />
  </Row>

  <Row>
    <RecipeFor id="printed_calculation_processor" />

    <RecipeFor id="printed_engineering_processor" />
  </Row>

  <br />

  3. **最终组装成型**

  <Row>
    <RecipeFor id="logic_processor" />

    <RecipeFor id="calculation_processor" />
  </Row>

  <RecipeFor id="engineering_processor" />
</Column>