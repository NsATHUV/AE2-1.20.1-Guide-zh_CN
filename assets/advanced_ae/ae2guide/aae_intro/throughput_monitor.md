---
navigation:
  parent: aae_intro/aae_intro-index.md
  title: ME吞吐量监控器
  icon: advanced_ae:throughput_monitor
categories:
  - advanced items
item_ids:
  - advanced_ae:throughput_monitor
  - advanced_ae:throughput_monitor_configurator
---

# ME吞吐量监控器

<GameScene zoom="8" background="transparent">
<ImportStructure src="../structure/throughput_monitors.snbt"></ImportStructure>
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

吞吐量监控器是监控器的一个子类。它在具备<ItemLink id="ae2:storage_monitor" />所有功能的基础上，增加了吞吐量计量功能。可追踪指定物品/流体类型的数量变化，并向用户显示每秒的吞吐量数值。

该设备*不需要*占用频道。

## 操作方式

* 手持物品右击 或 手持流体容器双击右击 —— 设定监控目标
* 空手右击 —— 清空监控目标
* 空手Shift+右击 —— 锁定当前监控目标

## 吞吐量监控配置器

<ItemImage id="advanced_ae:throughput_monitor_configurator" scale="4"></ItemImage>

此工具用于切换监控数据显示模式。对监控器右击可循环切换三种模式：

* 物品每刻（20刻=1秒）
* 物品每秒
* 物品每分钟

注意：模式切换后初始读数可能不稳定，请等待数值稳定后再参考！