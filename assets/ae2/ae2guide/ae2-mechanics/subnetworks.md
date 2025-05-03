---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 子网络系统
---

# 子网络系统

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/subnet_demonstration.snbt" />

<DiamondAnnotation pos="6.5 2.5 0.5" color="#00ff00">
        物品管道子网
</DiamondAnnotation>

<DiamondAnnotation pos="5.5 2.5 0.5" color="#00ff00">
        流体管道子网
</DiamondAnnotation>

<DiamondAnnotation pos="4.5 2.5 0.5" color="#00ff00">
        过滤型ME破坏面板
</DiamondAnnotation>

<DiamondAnnotation pos="3.5 2.5 0.5" color="#00ff00">
        ME成型面板子网
</DiamondAnnotation>

<DiamondAnnotation pos="2.5 2.5 0.5" color="#00ff00">
        接口-存储总线联动物联网（主网络可访问的本地二级存储）
</DiamondAnnotation>

<DiamondAnnotation pos="1.5 1.5 0.5" color="#00ff00">
        物品回传子网（将充能物品送回ME样板供应器）
</DiamondAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 核心概念

子网络是辅助主网络运行的独立单元，通常无需控制器即可运作。主要功能包括：

* **存储权限控制**  
  限制[设备](../ae2-mechanics/devices.md)访问范围（例如防止管道子网的ME输入总线将物品存入主网络存储元件）

* **频道资源优化**  
  通过单频道服务多设备（如1个ME样板供应器通过接口连接多台机器的存储总线）

## 网络隔离特性

* 不同颜色线缆仅物理隔离，不影响逻辑网络划分
* 推荐使用定向设备（如定向ME样板供应器）实现逻辑隔离

## 典型应用场景

* **智能传输系统**  
  ME输入总线+存储总线组合，模拟物品/流体管道功能

* **精准采集模块**  
  ME破坏面板+过滤存储总线，实现指定方块采集

* **自动化建造单元**  
  ME接口+ME成型面板，实现网络物品实体化

* **赛特斯石英农场**  
  主网络ME标准发信器调控子网自动生产

* **独立仓储方案**  
  通过接口与存储总线联动构建隔离存储空间

* **充能回传网络**  
  专用子网处理充能物品回收流程

## 能源解决方案

<ItemLink id="quartz_fiber" />（石英纤维）是子网关键组件：
- 跨网络传输能源
- 保持网络独立性
- 无需额外配置能源接收器

- 设计技巧：将高频操作设备部署在子网可提升主网稳定性