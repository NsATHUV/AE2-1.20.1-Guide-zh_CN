---
navigation:
  parent: example-setups/example-setups-index.md
  title: 矿物时运自动化处理
  icon: minecraft:raw_iron
---

# 矿物时运自动化处理

<ItemLink id="annihilation_plane" />可附加镐类附魔（包括时运），配合<ItemLink id="formation_plane" />和<ItemLink id="annihilation_plane" />可实现矿物快速放置与高效采集。

注意：<ItemLink id="import_bus" />存在预热机制，系统启动时会逐步提升至全速状态。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 0 2" max="3 1 3">
        (1) ME输入总线：安装多张加速卡
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 2" max="2 1 2.3">
        (2) ME成型面板：保持默认配置
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 0.7" max="2 1 1">
        (3) ME破坏面板：附魔时运III（无需配置界面）
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 0 0" max="3 1 1">
        (4) 存储总线：保持默认配置
  </BoxAnnotation>

<DiamondAnnotation pos="3.5 0.5 2.5" color="#00ff00">
        输入端
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 0.5 0.5" color="#00ff00">
        输出端
    </DiamondAnnotation>

<DiamondAnnotation pos="4 0.5 1.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* <ItemLink id="import_bus" /> (1)  
  安装<ItemLink id="speed_card" />（加速卡数量与成型面板数量成正比）

* <ItemLink id="formation_plane" /> (2)  
  保持默认配置

* <ItemLink id="annihilation_plane" /> (3)  
  附魔时运III（无需界面配置）

* <ItemLink id="storage_bus" /> (4)  
  保持默认配置

## 工作原理

1. **原料输入阶段**  
   绿色子网的ME输入总线从木桶提取原始矿物至[网络存储](../ae2-mechanics/import-export-storage.md)

2. **矿物部署阶段**  
   子网中唯一的存储端ME成型面板将矿物部署至采集区

3. **高效采集阶段**  
   橙色子网的ME破坏面板破碎矿物并应用时运效果

4. **成果收集阶段**  
   存储总线将产物存入输出端木桶

- 效率提示：每增加一个成型面板需对应增加加速卡
- 注意事项：时运等级直接影响产物数量