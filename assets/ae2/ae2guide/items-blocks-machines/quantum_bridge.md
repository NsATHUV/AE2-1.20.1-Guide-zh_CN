---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 量子网桥
  icon: quantum_ring
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:quantum_link
- ae2:quantum_ring
---

# 量子网桥

![量子网桥示意图](../assets/diagrams/quantum_bridge_demonstration.png)

量子网桥可实现[ME网络](../ae2-mechanics/me-network-connections.md)的无限距跨维度连接。该结构总共可承载32个频道（与各面线缆连接方式无关），本质上相当于无线[致密线缆](cables.md#dense-cable)。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_2.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="6 2 3">
        两端之间的虚拟线缆连接
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

重要提示：**两端必须保持区块加载**，若距离过远需使用<ItemLink id="spatial_anchor" />或其他区块加载器。

# 量子环

<BlockImage id="quantum_ring" scale="8" />

8个量子环围绕<ItemLink id="quantum_link" />可构建量子网络桥。仅4个与链接仓直接相邻的量子环可连接网络，角落的4个量子环无法连接线缆。

## 合成配方

<RecipeFor id="quantum_ring" />

# 量子链接仓

<BlockImage id="quantum_link" scale="8" />

该方块被<ItemLink id="quantum_ring" />环绕后形成量子网络桥。链接仓本身无法连接线缆，仅在完整结构建成后接入网络。

链接仓库存仅可存放1个<ItemLink id="quantum_entangled_singularity" />，支持自动化访问。

## 合成配方

<RecipeFor id="quantum_link" />