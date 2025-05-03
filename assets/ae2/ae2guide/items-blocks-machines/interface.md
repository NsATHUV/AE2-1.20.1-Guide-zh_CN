---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME接口
  icon: interface
  position: 210
categories:
- devices
item_ids:
- ae2:interface
- ae2:cable_interface
---

# ME接口

<Row gap="20">
<BlockImage id="interface" scale="8" />
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_interface.snbt" />
</GameScene>
</Row>

接口的作用类似于小型箱体/流体储罐，能够根据槽位设置从[网络存储](../ae2-mechanics/import-export-storage.md)自动补充或清空物品。其单游戏刻可处理多达9组物品，若搭配高速管道可实现快速输入输出。

另一个重要特性是，接口最多可存储9种不同流体（普通储罐仅能存1种），同时兼具物品存储功能。本质上它们是带有增强功能的箱体/复合储罐，断开网络连接时仍可作为普通容器使用。

## 内部工作机制

接口本质上是一个集成多组超强<ItemLink id="import_bus" />和<ItemLink id="export_bus" />，并配备多组<ItemLink id="level_emitter" />的复合设备：

<GameScene zoom="3" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_internals.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 0.3 1.3" max="9.7 1 1.7">
        控制库存数量的多组电平发信器
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/level_emitter.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 4 1.3" max="9.7 4.7 1.7">
        控制库存数量的多组电平发信器
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/level_emitter.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 1.3 1.3" max="9.7 2 1.7">
        单游戏刻可传输1组物品的超级输入总线阵列
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/import_bus.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 3 1.3" max="9.7 3.7 1.7">
        单游戏刻可传输1组物品的超级输出总线阵列
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/export_bus.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="10 3 2">
        9个独立存储槽位
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="15" />
</GameScene>

## 特殊交互

接口与其他AE2[设备](../ae2-mechanics/devices.md)有以下特殊交互：

* 在未配置的接口上安装<ItemLink id="storage_bus" />时，存储总线将直接访问该接口所在网络的[全部存储](../ae2-mechanics/import-export-storage.md)，如同将存储总线安装在网络本身。若接口设置库存物品，此功能将被禁用。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_storage.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

* [子网](../ae2-mechanics/subnetworks.md)中的样板供应器与接口存在特殊交互：未配置的接口将允许供应器直接推送物品至子网存储，跳过接口槽位填充，且仅在存储有空位时才会推送新批次。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        接口（必须为扁平版）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        存储总线阵列
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        目标机器（可多台或多面输入）
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## 变体类型

接口有两种形态：标准版和扁平版/[子部件](../ae2-mechanics/cable-subparts.md)：

* **标准接口**：允许所有面进行物品存取，并提供全向网络连接
* **扁平接口**：作为线缆子部件，可密集排布。仅允许正面存取物品，且不提供正面网络连接

两者可通过合成相互转换。

## 设置项

* 上方9个槽位定义需要维持的库存物品/流体
* 右键流体容器（如桶）可设置流体过滤
* 点击槽位旁的扳手设置库存数量

## 可安装升级

接口支持以下[升级卡](upgrade_cards.md)：
* <ItemLink id="fuzzy_card" /> 启用模糊匹配（按耐久或忽略NBT）
* <ItemLink id="crafting_card" /> 启用自动合成请求，优先从存储提取，不足时触发[自动合成](../ae2-mechanics/autocrafting.md)

## 优先级设置

点击GUI右上角扳手设置优先级，高优先级接口优先获取物品。

## 合成配方

<Recipe id="network/blocks/interfaces_interface" />

<RecipeFor id="cable_interface" />