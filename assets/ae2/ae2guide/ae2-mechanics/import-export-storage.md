---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 输入、输出与存储
---

# 输入、输出与存储

**ME系统与世界的交互**

网络存储是AE2中的重要概念。它是网络中的内容物的存放位置，通常位于[存储元件](../items-blocks-machines/storage_cells.md)或是与<ItemLink id="storage_bus" />相连的容器中。多数AE2[设备](../ae2-mechanics/devices.md)都与它有这样那样的交互。

例如

*   <ItemLink id="import_bus" />把物品送入网络存储；
*   <ItemLink id="export_bus" />从网络存储中获取物品；
*   <ItemLink id="interface" />可同时送入和获取物品；
*   [终端](../items-blocks-machines/terminals.md)在你放入或拿出物品时送入或获取物品，并自动填充合成网格；
*   <ItemLink id="storage_bus" />实际上并不从网络存储中送入或获取物品，它们从相邻容器中送入或获取，将其用作网络存储的一部分(因此实际上是其他元件从**它们**这儿送入或获取物品)。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_export_storage.snbt" />

  <BoxAnnotation color="#dddddd" min="8 1 1" max="9 1.3 2">
        输入总线从它们面向的容器中提取物品送入网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="8 2 1" max="9 3 1.3">
        从你的物品栏里把物品放入网络算作物品被送入网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="7 0 1" max="8 1 2">
        如果相应槽位未被配置或是存储量超过配置量，接口会将它的内部储存送入网络，因此可将物品送入其中以将其送入网络
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="6 0 1" max="7 1 2">
        样板供应器会把产物返回栏内的物品送入网络，因此可将物品送入其中以将其送入网络
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 1" max="5 2 2">
        驱动器把其中的存储元件用于网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="4 1.3 2">
        存储总线把其面向的容器用作网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 1 1" max="2 1.3 2">
        输出总线从网络存储中获取物品并送入它们面向的容器中
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="2 3 1.3">
        在终端处从网络里把物品取出算作物品被送出网络存储
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 1 1" max="1 2 2">
        如果相应槽位被配置为存储某物，接口会从网络中获取物品并存储在其内部存储中，因此可从中获取物品以从网络中获取物品
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

物品进入/离开网络的行为和事件应当牢记于心，这对于自动化和物流设计十分重要。

## 存储优先级

点击部分GUI右上角的扳手可设置相应设备的优先级。进入网络的物品会先进入最高优先级的网络存储设备。
当两个或多个网络存储设备优先级相同时，物品会优先进入已经有相同物品的存储设备。
当元件位于一族储存在与其他设备优先级相同的设备中的元件中时，已列入白名单的元件会被视为已有相同物品。
离开网络的物品会优先来自最低优先级的网络存储设备。优先级系统意味着，随着物品进出网络存储，高优先级设备会逐渐被占满而低优先级设备会逐渐被清空。
