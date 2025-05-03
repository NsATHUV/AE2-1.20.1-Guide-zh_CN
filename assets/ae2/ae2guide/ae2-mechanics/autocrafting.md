---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 自动合成系统
  icon: pattern_provider
---

# 自动合成系统

### 核心功能展示

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/autocraft_setup_greebles.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

作为AE2的核心功能，自动合成系统让您告别手动合成时代。无论是复杂配方逐级合成、定时定量生产，还是智能库存管理，这套系统都能完美胜任。支持流体处理，配合扩展模组还能操作特殊材料（如Mekanism气体）。

## 核心三要素

- **请求源**：终端操作/自动设备触发
- **合成CPU**：任务管理中心
- **ME样板供应器**：执行生产指令

### 工作流程

1. **发起请求**  
   - 终端点击可自动合成物品
   - 安装合成卡的设备触发需求（如输出总线/接口）

   - 小技巧：使用"选取方块"键（默认中键）可强制补货已有物品

2. **任务规划**  
   系统自动分解配方树，将所需材料暂存选定CPU

3. **指令执行**  
   ME样板供应器根据[样板](../items-blocks-machines/patterns.md)推送材料：
   - 合成类配方：输送至<ItemLink id="molecular_assembler" />
   - 加工类配方：对接各类加工设备

4. **成果回收**  
   通过输入总线/接口等方式回传产物  
 ‼ 必须触发"物品入网"事件，单纯存入带存储总线的箱子无效

5. **级联处理**  
   中间产物自动用于后续合成步骤

---

# 样板系统

<ItemImage id="crafting_pattern" scale="4" />

在<ItemLink id="pattern_encoding_terminal" />中用空白样板制作

### 四大样板类型

* **合成样板**  
  对应工作台配方，可直接插入<ItemLink id="molecular_assembler" />  
  推荐搭配ME样板供应器使用，实现全自动流水线

***

* **锻造样板**  
  处理锻造台配方，工作逻辑与合成样板完全一致

***

* **切石样板**  
  对应切石机配方，三类基础样板可混用同一系统

***

* **处理样板**  
  开放式配方系统，支持任意加工流程：
  - 可对接任何模组机器
  - 允许魔改配方（如1樱桃木板=1下界之星）
  - 支持批量处理（8圆石→8石头）

---

# 高级配方控制

<ItemLink id="level_emitter" />+合成卡可创建"红石信号配方"：
- 不限定输入材料
- 收到指定物品即触发信号
- 适用于无限资源生产（如圆石复制机）

---

# 合成CPU架构

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

### 核心组件

- **存储单元**（必需）：1k/4k/16k/64k/256k规格  
  决定单任务最大复杂度
- **协处理器**（可选）：提升并行处理能力
- **监控器**（可选）：实时查看任务状态
- **填充单元**（可选）：构建完整多方块结构

每个CPU独立处理单个任务，支持设置处理权限（玩家/自动化/全部）

---

# ME样板供应器

<Row>
<BlockImage id="pattern_provider" scale="4" />
<BlockImage id="pattern_provider" p:push_direction="up" scale="4" />
<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

### 三大形态

1. **标准型**  
   - 全向推送材料
   - 接收各面输入
   - 提供网络连接

2. **定向型**（使用扳手调整）  
   - 单面推送
   - 屏蔽连接面网络
   - 适合构建子网

3. **紧凑型**（线缆组件）  
   - 多设备共线安装
   - 功能同定向型

### 智能设置

- **阻塞模式**：设备未清空前暂停推送
- **合成锁定**：红石条件控制
- **终端可见性**：配置<ItemLink id="pattern_access_terminal" />显示

优先级系统确保高效配方选择，紧急订单自动优选

---

# 分子装配室

<BlockImage id="molecular_assembler" scale="4" />

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

### 核心功能

- 解析相邻样板供应器的指令
- 自动将成品推送至周边容器
- 支持直接插入合成/锻造/切石样板

高效布局方案：  
棋盘式排列实现紧凑并行处理，每8台为一组优化频道使用