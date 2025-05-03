---
navigation:
  parent: example-setups/example-setups-index.md
  title: 熔炉自动化
  icon: minecraft:furnace
---

# 熔炉自动化

本方案通过<ItemLink id="pattern_provider" />实现与[自动合成系统](../ae2-mechanics/autocrafting.md)的集成。若只需基础自动化，可使用漏斗+箱子等传统方式。

熔炉自动化比[充能器](../example-setups/charger-automation.md)等简单设备更复杂，需要三面交互：顶部输入原料、侧面输入燃料、底部输出成品。传统方案需占用3个[频道](../ae2-mechanics/channels.md)，本方案仅需1个：

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) ME样板供应器：使用赛特斯石英扳手调整为定向模式，配置处理样板

        ![铁锭合成样板](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) ME接口：保持默认配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) 存储总线#1：过滤设置为煤炭
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) 存储总线#2：使用<ItemLink id="inverter_card" />设置煤炭黑名单
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* <ItemLink id="pattern_provider" /> (1) 保持默认配置，需配置<ItemLink id="processing_pattern" />。使用<ItemLink id="certus_quartz_wrench" />调整为定向模式

  ![铁锭合成样板](../assets/diagrams/furnace_pattern.png)

* <ItemLink id="interface" /> (2) 保持默认配置
* 第一个<ItemLink id="storage_bus" /> (3) 过滤设置为煤炭（或其他燃料）
* 第二个<ItemLink id="storage_bus" /> (4) 使用<ItemLink id="inverter_card" />设置燃料黑名单

## 工作原理

1. <ItemLink id="pattern_provider" />将原料推送至<ItemLink id="interface" />（实际通过存储总线直接输送，不经过接口）
2. 接口设置为不存储物品，将原料推送至[网络存储](../ae2-mechanics/import-export-storage.md)
3. 子网中两个<ItemLink id="storage_bus" />分工协作：过滤煤炭的总线通过侧面填充燃料，黑名单煤炭的总线通过顶部填充原料
4. 熔炉完成冶炼过程
5. 漏斗从底部提取成品，通过样板供应器返回主网络