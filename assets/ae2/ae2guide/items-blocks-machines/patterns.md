---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 样板
  icon: crafting_pattern
  position: 410
categories:
- tools
item_ids:
- ae2:blank_pattern
- ae2:crafting_pattern
- ae2:processing_pattern
- ae2:smithing_table_pattern
- ae2:stonecutting_pattern
---

# 样板系统

<ItemImage id="crafting_pattern" scale="4" />

样板在<ItemLink id="pattern_encoding_terminal" />中使用空白样板制作，可插入<ItemLink id="pattern_provider" />或<ItemLink id="molecular_assembler" />实现自动化生产。

## 样板类型

### 合成样板

<ItemImage id="crafting_pattern" scale="4" />

* 编码工作台合成配方，可直接放入分子装配室实现即时合成
* 主要应用于样板供应器+分子装配室组合，供应器会推送原料至装配室并自动回收产物

***

### 锻造台样板

<ItemImage id="smithing_table_pattern" scale="4" />

* 编码锻造台升级配方，自动化流程与合成样板完全兼容
* 支持与合成/切石样板混用同一自动化产线

***

### 切石机样板

<ItemImage id="stonecutting_pattern" scale="4" />

* 编码切石机加工配方，操作逻辑与前述样板类型一致
* 可实现多类型样板混合自动化生产

***

### 处理样板

<ItemImage id="processing_pattern" scale="4" />

* 提供最高灵活度的广义合成方案，仅定义"投入原料→获取产物"关系
* 兼容所有模组机器及熔炉等原版设备，不限制中间工艺流程
* 支持自定义生产链（如"1樱花木板=1下界之星"的自动化指令触发）

## 高级特性

* **批量处理**：可配置8圆石=8石头的配方，实现单次操作批量投料
* **并行生产**：多个同配方样板供应器可协同工作提升效率

## 合成配方

<RecipeFor id="blank_pattern" />