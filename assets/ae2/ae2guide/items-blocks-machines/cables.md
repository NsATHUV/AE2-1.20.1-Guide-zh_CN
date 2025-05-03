---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME线缆
  icon: fluix_glass_cable
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:white_glass_cable
- ae2:orange_glass_cable
- ae2:magenta_glass_cable
- ae2:light_blue_glass_cable
- ae2:yellow_glass_cable
- ae2:lime_glass_cable
- ae2:pink_glass_cable
- ae2:gray_glass_cable
- ae2:light_gray_glass_cable
- ae2:cyan_glass_cable
- ae2:purple_glass_cable
- ae2:blue_glass_cable
- ae2:brown_glass_cable
- ae2:green_glass_cable
- ae2:red_glass_cable
- ae2:black_glass_cable
- ae2:fluix_glass_cable
- ae2:white_covered_cable
- ae2:orange_covered_cable
- ae2:magenta_covered_cable
- ae2:light_blue_covered_cable
- ae2:yellow_covered_cable
- ae2:lime_covered_cable
- ae2:pink_covered_cable
- ae2:gray_covered_cable
- ae2:light_gray_covered_cable
- ae2:cyan_covered_cable
- ae2:purple_covered_cable
- ae2:blue_covered_cable
- ae2:brown_covered_cable
- ae2:green_covered_cable
- ae2:red_covered_cable
- ae2:black_covered_cable
- ae2:fluix_covered_cable
- ae2:white_covered_dense_cable
- ae2:orange_covered_dense_cable
- ae2:magenta_covered_dense_cable
- ae2:light_blue_covered_dense_cable
- ae2:yellow_covered_dense_cable
- ae2:lime_covered_dense_cable
- ae2:pink_covered_dense_cable
- ae2:gray_covered_dense_cable
- ae2:light_gray_covered_dense_cable
- ae2:cyan_covered_dense_cable
- ae2:purple_covered_dense_cable
- ae2:blue_covered_dense_cable
- ae2:brown_covered_dense_cable
- ae2:green_covered_dense_cable
- ae2:red_covered_dense_cable
- ae2:black_covered_dense_cable
- ae2:fluix_covered_dense_cable
- ae2:white_smart_cable
- ae2:orange_smart_cable
- ae2:magenta_smart_cable
- ae2:light_blue_smart_cable
- ae2:yellow_smart_cable
- ae2:lime_smart_cable
- ae2:pink_smart_cable
- ae2:gray_smart_cable
- ae2:light_gray_smart_cable
- ae2:cyan_smart_cable
- ae2:purple_smart_cable
- ae2:blue_smart_cable
- ae2:brown_smart_cable
- ae2:green_smart_cable
- ae2:red_smart_cable
- ae2:black_smart_cable
- ae2:fluix_smart_cable
- ae2:white_smart_dense_cable
- ae2:orange_smart_dense_cable
- ae2:magenta_smart_dense_cable
- ae2:light_blue_smart_dense_cable
- ae2:yellow_smart_dense_cable
- ae2:lime_smart_dense_cable
- ae2:pink_smart_dense_cable
- ae2:gray_smart_dense_cable
- ae2:light_gray_smart_dense_cable
- ae2:cyan_smart_dense_cable
- ae2:purple_smart_dense_cable
- ae2:blue_smart_dense_cable
- ae2:brown_smart_dense_cable
- ae2:green_smart_dense_cable
- ae2:red_smart_dense_cable
- ae2:black_smart_dense_cable
- ae2:fluix_smart_dense_cable
---

# ME线缆

<GameScene zoom="3" background="transparent">
  <ImportStructure src="../assets/assemblies/cables.snbt" />
  <IsometricCamera yaw="180" pitch="30" />
</GameScene>

ME网络可通过相邻的ME兼容设备建立，而线缆是扩展ME网络覆盖范围的主要方式。

不同颜色的线缆可防止相邻线缆自动连接，优化[频道](../ae2-mechanics/channels.md)分配。线缆颜色同时影响所连接终端的配色（福鲁伊克斯色线缆可连接所有颜色）。

**重要提示：频道分配与线缆颜色无关**

## 给新手的建议

**若您不熟悉频道机制，请优先使用智能线缆和致密智能线缆。它们可直观显示频道路径，帮助理解网络结构。**

## 功能说明

**这些线缆并非传统意义上的物流管道。** 它们没有内部存储，设备之间通过线缆建立网络连接而非物品传输。

---

## 玻璃线缆

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/fluix_glass_cable.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="fluix_glass_cable" />是最基础的线缆，支持能量传输和8个[频道](../ae2-mechanics/channels.md)。提供17种配色（默认福鲁伊克斯色），可用染料染色。

染色方法：
- 工作台：8个同类型线缆+任意染料
- 游戏内：使用兼容的染色工具
- 浸入水桶可褪色

可升级为<ItemLink id="fluix_covered_cable" />（包层线缆）或<ItemLink id="fluix_smart_cable" />（智能线缆）

<RecipeFor id="fluix_glass_cable" />

<RecipeFor id="blue_glass_cable" />

---

## 包层线缆

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

与玻璃线缆功能相同，仅外观差异。可通过红石和荧石升级为<ItemLink id="fluix_covered_dense_cable" />（致密包层线缆）

<Recipe id="network/cables/covered_fluix" />

<RecipeFor id="blue_covered_cable" />

---

## 致密线缆

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

高容量线缆，支持32个频道。使用时需注意：
1. 无法直接连接设备总线
2. 需通过普通线缆中转
3. 频道优先选择最短致密路径

<Recipe id="network/cables/dense_covered_fluix" />

<RecipeFor id="blue_covered_dense_cable" />

---

## 智能线缆

<Row>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
</Row>

可视化诊断功能：
- 普通智能线缆：前4个频道显示线缆颜色，后4个显示白色条纹
- 致密智能线缆：每条纹代表4个频道
- 含控制器的网络：显示频道实际路径
- 临时网络：显示全网已用频道数

<Recipe id="network/cables/smart_fluix" />

<Recipe id="network/cables/dense_smart_fluix" />

<RecipeFor id="blue_smart_cable" />