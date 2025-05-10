---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME无线连接器
    icon: expatternprovider:wireless_connect
categories:
- extended devices
item_ids:
- expatternprovider:wireless_connect
- expatternprovider:wireless_tool
---

# ME无线连接器

<Row gap="20">
<BlockImage id="expatternprovider:wireless_connect" scale="6"></BlockImage>
<ItemImage id="expatternprovider:wireless_tool" scale="6"></ItemImage>
</Row>

ME无线连接器可建立类似<ItemLink id="ae2:quantum_link" />的网络链路，但存在以下限制：
- 有效传输距离有限
- 不支持跨维度连接

## 建立连接

使用ME无线配置工具按顺序点击两个连接器：
1. 手持<ItemImage id="expatternprovider:wireless_tool" scale="2"></ItemImage>
2. 右键点击第一个连接器（绑定坐标）
3. 右键点击第二个连接器（建立链路）

潜行+点击工具可清除当前配置

成功建立连接后，连接器纹理将发生变化：

未连接状态：
<GameScene zoom="5" background="transparent">
  <ImportStructure src="../structure/wireless_connector_off.snbt"></ImportStructure>
</GameScene>

已连接状态：
<GameScene zoom="5" background="transparent">
  <ImportStructure src="../structure/wireless_connector_on.snbt"></ImportStructure>
</GameScene>

## 染色系统
- 使用<ItemLink id="ae2:color_applicator" />进行染色
- 仅允许同色连接器/线缆间建立连接
- 支持16色通道隔离

典型应用场景：
<GameScene zoom="3" background="transparent" interactive={true}>
  <ImportStructure src="../structure/wireless_connector_setup.snbt"></ImportStructure>
</GameScene>

## 能量消耗
- 基础能耗公式：能耗 = 10^(距离/50) AE/t
- 最大有效距离：128格（基础值）
- 每安装1张<ItemLink id="ae2:energy_card" />降低10%能耗
- 满级配置（4张升级卡）最大距离扩展至256格