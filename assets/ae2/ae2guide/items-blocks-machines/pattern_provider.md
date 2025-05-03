---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME样板供应器
  icon: pattern_provider
  position: 210
categories:
- devices
item_ids:
- ae2:pattern_provider
- ae2:cable_pattern_provider
---

# ME样板供应器

<Row gap="20">
<BlockImage id="pattern_provider" scale="8" />
<BlockImage id="pattern_provider" p:push_direction="up" scale="8" />
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

样板供应器是[自动合成系统](../ae2-mechanics/autocrafting.md)与外界交互的核心设备。它将[样板](patterns.md)中的原料推送至相邻容器，并能接收物品存入网络。相比使用<ItemLink id="import_bus" />，将机器产物直接回传至供应器可节省频道资源。

重要特性：
* 原料直接从[合成存储单元](crafting_cpu_multiblock.md#crafting-storage)推送，供应器自身不存储材料
* 必须一次性推送整批原料，不支持分批处理
* 与[子网](../ae2-mechanics/subnetworks.md)接口配合时，直接推送至子网存储

典型应用：熔炉自动化（同时推送原料和燃料）

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) 定向样板供应器：使用赛特斯石英扳手调整方向，装载加工样板

        ![铁锭加工样板](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) ME接口：保持默认配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) 存储总线#1：过滤煤炭
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) 存储总线#2：黑名单模式（使用反相卡）
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

多机器并行处理方案：

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        扁平接口
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        存储总线阵列
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        目标机器组
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## 设备变体

* **标准型**：全向推送/接收，提供全向网络连接
* **定向型**：用<ItemLink id="certus_quartz_wrench" />调整方向，单面推送且不提供该面网络连接
* **扁平型**：[线缆子部件](../ae2-mechanics/cable-subparts.md)，支持密集排布，单面功能

## 核心设置

* **阻塞模式**：目标容器存在原料时暂停推送
* **合成锁定**：根据红石信号或产物返回状态锁定
* **终端可见性**：控制是否在<ItemLink id="pattern_access_terminal" />显示

## 优先级设置

点击GUI右上角扳手图标设置优先级。当多个样板匹配时，高优先级供应器优先使用（需原料充足）。

## 常见误区

错误配置示例（线缆无法接收物品）：

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_1.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        非高炉结构
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

正确配置应直接连接目标机器：

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_3.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        非高炉结构
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

## 合成配方

<RecipeFor id="pattern_provider" />

<RecipeFor id="cable_pattern_provider" />