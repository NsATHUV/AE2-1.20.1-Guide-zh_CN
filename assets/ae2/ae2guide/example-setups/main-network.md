---
navigation:
  parent: example-setups/example-setups-index.md
  title: 主网络示例布局
  icon: controller
---

# 主网络示例布局

当其他方案提及"主网络"时，您可能好奇这些[设备](../ae2-mechanics/devices.md)如何协同运作。以下展示一个典型配置：

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="3.9 0 1.9" max="9.1 5 7.1" thickness="0.05">
        ▶ 核心合成区
        - ME样板供应器与分子装配室集群
        - 棋盘式布局实现紧凑并行合成
        - 每8台为一组，完美规避频道冲突
        - 支持合成/切石/锻造等多类型样板
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="3.9 0 9.9" max="5.1 3 12.1" thickness="0.05">
        ▶ 工业处理区
        - 各类加工设备（熔炉/粉碎机等）
        - 通过管道子网将产物回传供应器
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="-0.1 0 8.9" max="1.1 3 13.1" thickness="0.05">
        ▶ 终端交互区
        - 合成终端为核心（普通终端可酌情配置）
        - 配套各类实用小工具
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="-0.1 0 -0.1" max="2.1 3 8.1" thickness="0.05">
        ▶ 合成CPU矩阵
        - 混合配置不同存储容量的处理单元
        - 建议实际部署时增加协处理器数量
        - 演示场景受空间限制适当精简
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5.9 0 13.9" max="7.1 1 15.1" thickness="0.05">
        ▶ 控制器中枢
        - 应位于基地中心区域
        - 推荐采用柱状结构扩展（演示模型较精简）
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="11.9 0 7.9" max="13.1 4 13.1" thickness="0.05">
        ▶ 仓储解决方案A
        - ME驱动器阵列与存储总线组合
        - 严格遵循8设备分组原则
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="10.9 0 0.9" max="13.1 2 7.1" thickness="0.05">
        ▶ 仓储解决方案B
        - 多元化存储方案混搭
        - 每组8台确保频道优化
    </BoxAnnotation>

  <IsometricCamera yaw="315" pitch="30" />
</GameScene>