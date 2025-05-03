---
navigation:
  parent: example-setups/example-setups-index.md
  title: 标准发信器智能补货系统
  icon: level_emitter
---

# 标准发信器智能补货系统

当玩家需要维持某种物品的稳定库存时，如何实现缺货自动补足？本方案采用<ItemLink id="export_bus" />、<ItemLink id="level_emitter" />与<ItemLink id="crafting_card" />的黄金组合，通过[自动合成系统](../ae2-mechanics/autocrafting.md)实现精准调控。特别适合大规模单一物资的仓储管理。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/level_emitter_autostocking.snbt" />

  <BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (1) 输出总线：锁定目标物品，搭载红石卡+合成卡双模块
        <Row><ItemImage id="redstone_card" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
        ▶ 红石响应模式：有信号激活 | 合成策略：跳过现有库存
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0.7 1 0" max="1 2 1">
        (2) 标准发信器：设定补货阈值
        ▶ 监控物品：铁锭 | 触发条件：存量＜512
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (3) 通用接口：保持出厂设置
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        主网络接入点
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 核心配置

* <ItemLink id="export_bus" /> (1)  
  - 物品过滤：设置目标物资（如铁锭）
  - 功能模块：安装<ItemLink id="redstone_card" />和<ItemLink id="crafting_card" />
  - 工作模式：  
    → 红石控制：收到信号才运作  
    → 合成策略：强制新建订单

* <ItemLink id="level_emitter" /> (2)  
  - 监控物品：选择需要补货的物资
  - 数量阈值：设置库存预警线（如低于512个时触发）
  - 信号模式：存量不足时亮起红石信号

* <ItemLink id="interface" /> (3)  
  - 无需特别设置，保持默认状态

## 运作流程

1. **库存监控**  
   当[网络仓储](../ae2-mechanics/import-export-storage.md)中铁锭存量跌破512时，标准发信器亮起红灯

2. **订单触发**  
   输出总线检测到红石信号后：  
   → 跳过现有库存直接发起[合成请求](../ae2-mechanics/autocrafting.md)  
   → 将新生产的铁锭输送至接口

3. **入库完成**  
   接口自动将收到的物资归库，库存量恢复到安全线以上

- 小技巧：移除标准发信器和红石卡可改为持续生产模式，适合消耗量稳定的物资