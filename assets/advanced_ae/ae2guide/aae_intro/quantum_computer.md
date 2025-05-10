---
navigation:
  parent: aae_intro/aae_intro-index.md
  title: 量子计算机
  icon: advanced_ae:quantum_core
categories:
  - advanced devices
item_ids:
  - advanced_ae:quantum_unit
  - advanced_ae:quantum_core
  - advanced_ae:quantum_structure
  - advanced_ae:quantum_accelerator
  - advanced_ae:quantum_multi_threader
  - advanced_ae:quantum_storage_128
  - advanced_ae:quantum_storage_256
  - advanced_ae:data_entangler
---

# 量子计算机

量子计算机是特殊的合成计算机。只要拥有足够的合成存储容量，它能够运行无限数量的合成请求。

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../structure/quantum_computer_multiblock.snbt"></ImportStructure>
</GameScene>

## 量子计算机核心

<BlockImage id="advanced_ae:quantum_core" p:powered="true" p:formed="true" scale="4"></BlockImage>

量子计算机核心是整个系统的核心部件。其本身具有256M合成存储空间和8个并行处理线程。它是唯一能独立构成量子计算机并提供所有功能的方块。若组建多方块结构，可创造更强大的计算机。单独使用时需通过顶部或底部的连接面供电。

## 量子存储单元

<Row gap="20">
<BlockImage id="advanced_ae:quantum_storage_128" scale="4"></BlockImage>
<BlockImage id="advanced_ae:quantum_storage_256" scale="4"></BlockImage>
</Row>

这些方块用于扩展量子核心的合成存储容量。可有效提升量子计算机的并行任务处理能力。提供128M和256M两种容量规格。

## 量子数据纠缠器

<BlockImage id="advanced_ae:data_entangler" scale="4"></BlockImage>

量子数据纠缠器是特殊功能方块，影响多方块结构中的所有存储单元。通过将数据存储至多个维度，使存储容量变为4倍。每个量子计算机多方块中最多放置1个。

## 量子计算机加速器

<BlockImage id="advanced_ae:quantum_accelerator" scale="4"></BlockImage>

量子加速器可为多方块结构增加8个并行处理线程。注意：所有合成任务均可共享所有并行处理单元，建议大量配置此部件。

## 量子多线程处理器

<BlockImage id="advanced_ae:quantum_multi_threader" scale="4"></BlockImage>

与数据纠缠器类似，多线程处理器使加速器可在不同维度运行额外线程，将并行处理能力提升4倍。每个量子计算机多方块中最多放置1个。

## 量子计算机外壳

<Row gap="20">
<BlockImage id="advanced_ae:quantum_structure" scale="4"></BlockImage>
<BlockImage id="advanced_ae:quantum_structure" p:formed="true" scale="4"></BlockImage>
<BlockImage id="advanced_ae:quantum_structure" p:formed="true" p:powered="true" scale="4"></BlockImage>
</Row>

这些方块构成量子计算机的框架结构。作为多方块结构的连接组件，将所有部件整合在一起。

## 多方块结构规则

组建量子计算机多方块需遵守以下规则：
- 最大外部尺寸为7x7x7；
- 内部不允许存在空隙，可用<ItemLink id="advanced_ae:quantum_unit" />填充（无额外增益）；
- 必须且仅能包含1个<ItemLink id="advanced_ae:quantum_core" />；
- 最多放置1个<ItemLink id="advanced_ae:data_entangler" />；
- 最多放置1个<ItemLink id="advanced_ae:quantum_multi_threader" />；
- 所有外层方块必须为<ItemLink id="advanced_ae:quantum_structure" />；
- 内部不允许存在量子计算机外壳。

## 服务器配置

管理员可通过配置文件调整以下参数：
- 最大多方块尺寸；
- 每个量子加速器的并行线程数；
- 多线程处理器的最大数量；
- 多线程处理器的线程倍增系数；
- 数据纠缠器的最大数量；
- 数据纠缠器的存储倍增系数；

具体参数限制可通过物品工具提示查看。