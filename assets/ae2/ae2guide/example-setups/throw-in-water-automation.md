---
navigation:
  parent: example-setups/example-setups-index.md
  title: 投水自动化
  icon: fluix_crystal
---

# 自动化投水配方

注意：本方案使用<ItemLink id="pattern_provider" />，需集成到[自动合成系统](../ae2-mechanics/autocrafting.md)中。

部分配方要求将物品投入水中（类似配置也可用于其他投掷场景）。可通过<ItemLink id="formation_plane" />、<ItemLink id="annihilation_plane" />及相关基础设施实现自动化（本质上是两个改进版[管道子网](pipe-subnet.md)）。

本方案建议与[充能自动化](charger-automation.md)配合使用，以提供<ItemLink id="charged_certus_quartz_crystal" />。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (1) ME样板供应器：默认配置，载入相关处理样板

        ![福鲁伊克斯样板](../assets/diagrams/fluix_pattern_small.png) ![有瑕母岩样板](../assets/diagrams/flawed_budding_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 1" max="2 1 2">
        (2) ME接口：默认配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 .7 1" max="2 1 2">
        (3) ME成型面板：设置为投掷物品模式
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 2 1" max="2 2.3 2">
        (4) ME破坏面板：无需配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (5) 存储总线：过滤配方产物
        <Row><ItemImage id="fluix_crystal" scale="2" /><BlockImage id="flawless_budding_quartz" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="3.9 0.5 1.5" color="#00ff00">
        连接主网络及充能自动化系统
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
    </DiamondAnnotation>

  <IsometricCamera yaw="180" pitch="0" />
</GameScene>

## 配置与样板设置

* <ItemLink id="pattern_provider" /> (1) 保持默认配置，载入相关<ItemLink id="processing_pattern" />
  * 制作<ItemLink id="fluix_crystal" />使用JEI/REI默认配方：

    ![福鲁伊克斯样板](../assets/diagrams/fluix_pattern.png)

  * 制作<ItemLink id="flawed_budding_quartz" />建议直接使用<ItemLink id="quartz_block" />作为原料，避免输入输出循环导致过滤失效：

    ![有瑕母岩样板](../assets/diagrams/flawed_budding_pattern.png)

* <ItemLink id="interface" /> (2) 保持默认配置
* <ItemLink id="formation_plane" /> (3) 设置为物品投掷模式
* <ItemLink id="annihilation_plane" /> (4) 无需配置
* <ItemLink id="storage_bus" /> (5) 过滤配方产物

## 工作原理

1. ME样板供应器将材料推送至绿色子网的ME接口
2. ME接口（默认不存储物品）尝试将内容物存入[网络存储](../ae2-mechanics/import-export-storage.md)
3. 绿色子网唯一存储为成型面板，将物品投入水中
4. 橙色子网的破坏面板尝试拾取物品，但因存储总线过滤产物而无法收取
5. 物品完成水中转化
6. 转化后的产物可通过存储总线识别，破坏面板开始收集
7. 存储总线将成品送回样板供应器，返回主网络