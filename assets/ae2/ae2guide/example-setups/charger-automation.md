---
navigation:
  parent: example-setups/example-setups-index.md
  title: 充能器自动化
  icon: charger
---

# 充能器自动化

本方案通过<ItemLink id="pattern_provider" />实现与[自动合成系统](../ae2-mechanics/autocrafting.md)的集成。若只需独立自动化<ItemLink id="charger" />，可使用漏斗+箱子等传统方式。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/charger_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) ME样板供应器：保持默认配置，需配置处理样板。同时作为线缆为充能器供电

        ![充能器样板](../assets/diagrams/charger_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="1 1.3 1">
        (2) ME输入总线：保持默认配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (3) 存储总线：保持默认配置
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* <ItemLink id="pattern_provider" /> (1) 保持默认配置，需配置<ItemLink id="processing_pattern" />。同时作为[线缆](../items-blocks-machines/cables.md)为充能器提供[能源](../ae2-mechanics/energy.md)
  
    ![充能器样板](../assets/diagrams/charger_pattern.png)

* <ItemLink id="import_bus" /> (2) 保持默认配置
* <ItemLink id="storage_bus" /> (3) 保持默认配置

## 工作原理

1. <ItemLink id="pattern_provider" />将原料推入<ItemLink id="charger" />
2. 充能器完成充能过程
3. 绿色子网的<ItemLink id="import_bus" />提取成品并存入[网络存储](../ae2-mechanics/import-export-storage.md)
4. 子网中唯一的存储端<ItemLink id="storage_bus" />将成品送回样板供应器，最终返回主网络