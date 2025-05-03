---
navigation:
  parent: example-setups/example-setups-index.md
  title: 专用本地存储
  icon: drive
---

# 专用本地存储

利用[ME接口的特殊交互机制](../items-blocks-machines/interface.md#special-interactions)，通过[子网](../ae2-mechanics/subnetworks.md)可将本地存储内容呈现给主网络，同时仅占用1个[频道](../ae2-mechanics/channels.md)，且无法访问主网络存储。

适用于农场等场景的本地存储，防止物品溢出至主存储。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/local_storage.snbt" />

<BoxAnnotation color="#dddddd" min="4 0 0" max="5 2 1">
        (1) 物品输入方式（本例使用ME接口）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 0 0" max="4 1 1">
        (2) ME驱动器：内置存储元件，元件需过滤农场产物。可安装均分卡和溢出销毁卡
        <Row><ItemImage id="item_storage_cell_4k" scale="2" /> <ItemImage id="equal_distribution_card" scale="2" /> <ItemImage id="void_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1 0" max="4 2 0.3">
        (3) 合成终端：仅查看子网驱动器内容，无法访问主网络存储
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 0" max="2.3 1 1">
        (4) ME接口#2：保持默认配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 0" max="2 1 1">
        (5) 存储总线：优先级高于主存储，可过滤农场产物
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 0.3">
        合成终端：可同时查看主网络存储和子网内容
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        连接主网络
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 配置说明

* ME接口#1 (1) 接收农场产物并推送至子网
* ME驱动器 (2) 内置[存储元件](../items-blocks-machines/storage_cells.md)，元件需[分区](../items-blocks-machines/cell_workbench.md)过滤农场产物，可安装<ItemLink id="equal_distribution_card" />和<ItemLink id="void_card" />
* ME接口#2 (4) 保持默认配置
* 存储总线 (5) 设置[优先级](../ae2-mechanics/import-export-storage.md#storage-priority)高于主存储，可过滤特定产物

## 工作原理

* 子网ME接口向主网络存储总线暴露驱动器内容，实现直接存取
* 存储总线高优先级确保产物优先存入子网
* 子网存储满载时物品不会溢出至主网络，可安装<ItemLink id="void_card" />自动销毁过量物品
* 多种产物共存时，<ItemLink id="equal_distribution_card" />可防止单一物品占满存储