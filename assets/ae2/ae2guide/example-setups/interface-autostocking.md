---
navigation:
  parent: example-setups/example-setups-index.md
  title: ME接口自动补货
  icon: interface
---

# ME接口自动补货

如何实现物品库存的动态维护？通过<ItemLink id="interface" />与<ItemLink id="crafting_card" />的组合，可自动触发[自动合成系统](../ae2-mechanics/autocrafting.md)按需补货。本方案特别适合维持多品种小批量的物品库存。

推荐使用4组<ItemLink id="interface" />+<ItemLink id="storage_bus" />组合，充分利用常规[线缆](../items-blocks-machines/cables.md)的8个[频道](../ae2-mechanics/channels.md)容量：

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_autostocking.snbt" />

<BoxAnnotation color="#dddddd" min="0 0 0" max="2 1 1">
        (1) ME接口：设置目标物品库存量，安装合成卡
        <ItemImage id="crafting_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="2 1.3 1">
        (2) 存储总线：输入/输出模式设为"仅取出"
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* <ItemLink id="interface" /> (1)：
  - 顶部槽位放置目标物品（支持JEI拖拽）
  - 点击扳手图标设置库存量
  - 安装<ItemLink id="crafting_card" />
* <ItemLink id="storage_bus" /> (2)：
  - 输入/输出模式设为"仅取出"

## 工作原理

1. 当<ItemLink id="interface" />检测到[网络存储](../ae2-mechanics/import-export-storage.md)中某物品数量不足时
2. 通过<ItemLink id="crafting_card" />触发[自动合成](../ae2-mechanics/autocrafting.md)流程
3. <ItemLink id="storage_bus" />以只读模式将接口库存接入主网络