---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 合成CPU多方块结构（存储器/协处理器/监控器/单元）
  icon: 1k_crafting_storage
  position: 210
categories:
- devices
item_ids:
- ae2:1k_crafting_storage
- ae2:4k_crafting_storage
- ae2:16k_crafting_storage
- ae2:64k_crafting_storage
- ae2:256k_crafting_storage
- ae2:crafting_accelerator
- ae2:crafting_monitor
- ae2:crafting_unit
---

# 合成CPU多方块结构

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="crafting_accelerator" scale="4" />

  <BlockImage id="crafting_monitor" scale="4" />

  <BlockImage id="crafting_unit" scale="4" />
</Row>

合成CPU负责管理[自动合成](../ae2-mechanics/autocrafting.md)任务，存储中间产物并影响合成规模与效率。每个CPU同时只能处理一个任务，多个任务需要多个CPU结构。

## 核心功能

* 存储合成过程的中间产物
* 通过右键点击查看合成进度
* 可配置接收玩家请求/自动化请求/二者兼有
* 最低配置：单个1k合成存储器

## 构造规则

必须构建为无空隙的实心长方体结构，至少包含1个合成存储器组件。

---

# 合成单元

<BlockImage id="crafting_unit" scale="4" />

（可选）用于填充CPU结构空间，也是其他组件的合成原料。

<RecipeFor id="crafting_unit" />

---

# 合成存储器

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="4k_crafting_storage" scale="4" />

  <BlockImage id="16k_crafting_storage" scale="4" />

  <BlockImage id="64k_crafting_storage" scale="4" />

  <BlockImage id="256k_crafting_storage" scale="4" />
</Row>

（必需）提供1k/4k/16k/64k/256k存储容量，决定CPU可处理的合成任务复杂度。

<Column>
  <Row>
    <RecipeFor id="1k_crafting_storage" />

    <RecipeFor id="4k_crafting_storage" />

    <RecipeFor id="16k_crafting_storage" />
  </Row>

  <Row>
    <RecipeFor id="64k_crafting_storage" />

    <RecipeFor id="256k_crafting_storage" />
  </Row>
</Column>

---

# 并行处理单元

<BlockImage id="crafting_accelerator" scale="4" />

（可选）提升<ItemLink id="pattern_provider" />的原料分发频率，适配高速处理设备（如被多个<ItemLink id="molecular_assembler" />环绕的样板供应器）。

<RecipeFor id="crafting_accelerator" />

---

# 合成监控器

<BlockImage id="crafting_monitor" scale="4" />

（可选）显示当前CPU处理的合成任务，支持<ItemLink id="color_applicator" />染色。

<RecipeFor id="crafting_monitor" />