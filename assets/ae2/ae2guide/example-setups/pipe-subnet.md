---
navigation:
  parent: example-setups/example-setups-index.md
  title: 物品/流体“管道”子网
  icon: storage_bus
---

# 物品/流体“管道”子网

本方案通过AE2[设备](../ae2-mechanics/devices.md)模拟传统管道功能，适用于需要将物品或流体从A点传输到B点的场景，例如将合成产物回传至<ItemLink id="pattern_provider" />。

## 核心配置方案

### 方案一：输入总线 → 存储总线

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) ME输入总线：可设置过滤
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) 存储总线：可设置过滤（需作为子网唯一存储端）
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        来源端
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        目标端
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

- **工作原理**  
  <ItemLink id="import_bus" /> (1) 从来源容器提取物品/流体至[网络存储](../ae2-mechanics/import-export-storage.md)  
  子网中唯一的<ItemLink id="storage_bus" /> (2) 将内容传输至目标容器  
  通过<ItemLink id="quartz_fiber" />提供能源

- **特性**  
  - 输入/输出端均可设置过滤
  - 支持多输入多输出配置

### 方案二：存储总线 → 输出总线

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) 存储总线：可设置过滤（需作为子网唯一存储端）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) ME输出总线：必须设置过滤
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        来源端
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        目标端
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

- **工作原理**  
  <ItemLink id="export_bus" />从目标端请求物品  
  子网中唯一的<ItemLink id="storage_bus" />从来源端提取内容  
  通过<ItemLink id="quartz_fiber" />提供能源

- **特性**  
  - 输出端必须设置过滤
  - 支持多来源多目标配置

## 无效配置示例

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_export_pipe.snbt" />

<BoxAnnotation color="#dd3333" min="3.7 0 0" max="4 1 1">
        ME输入总线：网络无存储导致无法导入
  </BoxAnnotation>

<BoxAnnotation color="#dd3333" min="1 0 0" max="1.3 1 1">
        ME输出总线：网络无存储导致无法导出
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#ff0000">
        来源端
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#ff0000">
        目标端
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

- **失效原因**  
  单纯连接输入总线和输出总线时，网络缺少存储单元导致传输中断

## 单面输入输出方案

针对类似<ItemLink id="charger" />的单面操作设备，可组合两种方案：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="4 1 1" max="5 1.3 2">
        (1) ME输入总线：可设置过滤
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (2) 存储总线：可设置过滤（需作为子网唯一存储端）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (3) 目标设备（示例为充能器）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 1" max="1 1.3 2">
        (4) ME输出总线：必须设置过滤
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 1.5" color="#00ff00">
        来源端
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 1.5" color="#00ff00">
        目标端
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## ME接口拓展应用

<ItemLink id="interface" />可通过以下方式增强管道功能：
- 未设置库存的物品自动推送至网络存储（类似输入总线）
- 设置库存的物品从网络存储提取（类似输出总线）

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/interface_pipes.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        ME接口
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.7 0 2" max="4 1 3">
        存储总线
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 2" max="1 1.3 3">
        存储总线
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 多对多传输架构

<GameScene zoom="3" background="transparent">
<ImportStructure src="../assets/assemblies/many_to_many_pipe.snbt" />

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

- 支持多输入源与多输出目标
- 通过存储总线矩阵实现复杂物流

## 多点分发方案

通过<ItemLink id="interface" />实现样板供应器到多目标的传输：

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        ME接口（需配置为紧凑型）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        存储总线阵列
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        多目标设备（单设备多面或多台设备）
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

- **配置要点**  
  - 样板供应器需设置为定向或紧凑型
  - ME接口需配置为紧凑型
  - 存储总线阵列连接各目标设备