---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 终端
  icon: crafting_terminal
  position: 210
categories:
- devices
item_ids:
- ae2:terminal
- ae2:crafting_terminal
- ae2:pattern_encoding_terminal
- ae2:pattern_access_terminal
---

# 终端系统

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/terminals.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

虽然<ItemLink id="pattern_provider" />（ME样板供应器）、<ItemLink id="import_bus" />（ME输入总线）和<ItemLink id="storage_bus" />（ME存储总线）等设备是AE2网络与外界交互的主要方式，但终端系统是网络与*玩家*交互的核心界面。各类终端提供不同功能。

终端颜色会继承所在[线缆](cables.md)的颜色。

终端属于[线缆子部件](../ae2-mechanics/cable-subparts.md)。

## 终端放置技巧

由于终端通常是玩家首次接触的[子部件](../ae2-mechanics/cable-subparts.md)，常见错误是反向安装。以下是正确与错误示例：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/terminal_placement.snbt" />
  <IsometricCamera yaw="195" pitch="30" />

  <LineAnnotation color="#ff3333" from="2.5 .5 .5" to="4.5 2.5 .5" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="2.5 2.5 .5" to="4.5 .5 .5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="-.5 2.5 .5" to="1 .5 .5" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1 .5 .5" to="1.5 1 .5" alwaysOnTop={true} thickness="0.05"/>
</GameScene>

正确布局不仅方向正确，还能更紧凑地接入网络，同时包含终端和能源接收器。

<a name="terminal-ui"></a>

# 基础终端

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

基础终端允许查看和操作[网络存储](../ae2-mechanics/import-export-storage.md)，并提交[自动合成](../ae2-mechanics/autocrafting.md)请求。

## 界面说明

基础终端界面分为多个功能区：

**中央区域**显示网络存储内容，支持存取操作：
- 左键点击获取整组，右键获取半组
- 对可[自动合成](../ae2-mechanics/autocrafting.md)物品使用"选取方块"键（默认中键）打开数量设置界面，支持输入公式如`3*64/2`，或`=32`表示补足库存至32个
- 按住Shift键冻结当前物品排列，防止数量变化时自动重排
- 右键使用桶等流体容器存入流体，左键点击流体用空容器提取

**左侧功能区**包含：
- 排序选项（名称/模组/数量等）
- 显示模式（已存储/可合成/全部）
- 物品类型过滤（物品/流体/全部）
- 排序顺序切换
- 终端详细设置
- 界面高度调节

**右侧插槽**用于放置<ItemLink id="view_cell" />（显示元件）

**右上角锤子按钮**显示[自动合成](../ae2-mechanics/autocrafting.md)状态，可查看各[合成CPU](crafting_cpu_multiblock.md)的工作进度。

## 合成配方

<RecipeFor id="terminal" />

<a name="crafting-terminal-ui"></a>

# 合成终端

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/crafting_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

合成终端在基础终端功能上增加合成网格，可自动从[网络存储](../ae2-mechanics/import-export-storage.md)补充材料。Shift+点击输出槽需谨慎！

建议尽早升级基础终端为合成终端。

## 界面说明

合成终端界面新增中央合成网格，包含两个功能按钮：
- 清空合成网格至网络存储
- 清空合成网格至玩家背包

## 合成配方

<RecipeFor id="crafting_terminal" />

<a name="pattern-encoding-terminal-ui"></a>

# 样板编码终端

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/pattern_encoding_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

样板编码终端用于编写[样板](patterns.md)，其合成网格仅用于配方记录，不执行实际合成。

建议与合成终端配合使用。

## 界面说明

**样板编码区**包含：
- <ItemLink id="blank_pattern" />（空白样板）输入槽
- 编码确认按钮（箭头图标）
- 已编码样板槽（可放入修改）
- 右侧四类样板切换标签（合成/处理/锻造/切石）

不同模式功能差异：

**合成模式**：
- 左键拖拽JEI/REI材料构建配方，右键移除材料
- 启用"材料替换"允许使用同类物品（如任意木板制作木棍），需谨慎使用
- 启用"流体替换"允许使用存储流体替代容器
- 支持从JEI/REI界面直接编码

**处理模式**：
- 左/右键设置输入输出材料
- 右键流体容器设置流体材料
- 左键整组操作，右键单个操作，中键精确设置数量
- 支持81种输入材料和26种副产物
- 主产物与副产物需明确区分
- 支持从JEI/REI界面直接编码

**锻造/切石模式**：界面分别对应锻造台和切石机布局。

## 合成配方

<RecipeFor id="pattern_encoding_terminal" />

<a name="pattern-access-terminal-ui"></a>

# 样板管理终端

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/pattern_access_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

样板管理终端解决两个核心问题：
1. 在密集的<ItemLink id="pattern_provider" />（ME样板供应器）阵列中远程存取样板
2. 避免长途跋涉手动操作样板

## 界面说明

该终端采用独特布局：
- 可调节界面高度
- 按连接设备或命名（使用铁砧或<ItemLink id="name_press" />）排序显示样板供应器
- 每行对应一个样板供应器，支持远程存取

## 合成配方

<RecipeFor id="pattern_access_terminal" />