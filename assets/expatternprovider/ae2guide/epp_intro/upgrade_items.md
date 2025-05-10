---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME设备升级卡
    icon: expatternprovider:pattern_provider_upgrade
categories:
- extended items
item_ids:
- expatternprovider:pattern_provider_upgrade
- expatternprovider:interface_upgrade
- expatternprovider:io_bus_upgrade
- expatternprovider:pattern_terminal_upgrade
- expatternprovider:drive_upgrade
---

# ME设备升级卡

实现设备无损升级的专用模块，可将常规ME设备转换为扩展版本并保留完整配置

<Row>
<ItemImage id="expatternprovider:pattern_provider_upgrade" scale="4"></ItemImage>
<ItemImage id="expatternprovider:interface_upgrade" scale="4"></ItemImage>
<ItemImage id="expatternprovider:io_bus_upgrade" scale="4"></ItemImage>
<ItemImage id="expatternprovider:pattern_terminal_upgrade" scale="4"></ItemImage>
<ItemImage id="expatternprovider:drive_upgrade" scale="4"></ItemImage>
</Row>

## 升级操作
潜行状态下右键点击目标设备，即可完成以下转换：
- 完整继承设备配置参数
- 保留全部存储内容
- 维持原有网络连接

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../structure/upgrade_show_1.snbt"></ImportStructure>
  <BoxAnnotation color="#ffffff" min="1 0 0" max="4 1 1">
        常规样板供应器，使用<ItemImage id="expatternprovider:pattern_provider_upgrade" scale="2"></ItemImage>进行升级
  </BoxAnnotation>
</GameScene>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../structure/upgrade_show_2.snbt"></ImportStructure>
  <BoxAnnotation color="#ffffff" min="1 0 0" max="4 1 1">
        升级后的扩展样板供应器完整保留原始配置与样板库存
  </BoxAnnotation>
</GameScene>

## 升级对照表

|                                       升级卡                                       |                             标准设备                             |                                扩展设备                                |
|:---------------------------------------------------------------------------------:|:---------------------------------------------------------------:|:---------------------------------------------------------------------:|
| <ItemImage id="expatternprovider:pattern_provider_upgrade" scale="3"></ItemImage> |    <ItemImage id="ae2:pattern_provider" scale="3"></ItemImage>     |   <ItemImage id="expatternprovider:ex_pattern_provider" scale="3"></ItemImage>    |
| <ItemImage id="expatternprovider:pattern_provider_upgrade" scale="3"></ItemImage> | <ItemImage id="ae2:cable_pattern_provider" scale="3"></ItemImage>  | <ItemImage id="expatternprovider:ex_pattern_provider_part" scale="3"></ItemImage> |
|    <ItemImage id="expatternprovider:interface_upgrade" scale="3"></ItemImage>     |        <ItemImage id="ae2:interface" scale="3"></ItemImage>        |       <ItemImage id="expatternprovider:ex_interface" scale="3"></ItemImage>       |
|    <ItemImage id="expatternprovider:interface_upgrade" scale="3"></ItemImage>     |     <ItemImage id="ae2:cable_interface" scale="3"></ItemImage>     |    <ItemImage id="expatternprovider:ex_interface_part" scale="3"></ItemImage>     |
|      <ItemImage id="expatternprovider:io_bus_upgrade" scale="3"></ItemImage>      |       <ItemImage id="ae2:import_bus" scale="3"></ItemImage>        |    <ItemImage id="expatternprovider:ex_import_bus_part" scale="3"></ItemImage>    |
|      <ItemImage id="expatternprovider:io_bus_upgrade" scale="3"></ItemImage>      |       <ItemImage id="ae2:export_bus" scale="3"></ItemImage>        |    <ItemImage id="expatternprovider:ex_export_bus_part" scale="3"></ItemImage>    |
| <ItemImage id="expatternprovider:pattern_terminal_upgrade" scale="3"></ItemImage> | <ItemImage id="ae2:pattern_access_terminal" scale="3"></ItemImage> |  <ItemImage id="expatternprovider:ex_pattern_access_part" scale="3"></ItemImage>  |
|      <ItemImage id="expatternprovider:drive_upgrade" scale="3"></ItemImage>       |          <ItemImage id="ae2:drive" scale="3"></ItemImage>          |         <ItemImage id="expatternprovider:ex_drive" scale="3"></ItemImage>         |