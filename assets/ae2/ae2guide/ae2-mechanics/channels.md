---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 频道
  icon: controller
---

# 频道

应用能源2的[ME网络](me-network-connections.md)需要频道来保证需要使用网络存储或其他网络服务的[设备](../ae2-mechanics/devices.md)。
把频道想象成连接到你所有设备的USB线。一台电脑只有那么多USB口，也就只能容纳那么多连接到它的设备。
大部分机器、占完整方块的设备以及普通线缆只能传递至多8个频道。可以把占完整方块的设备和标准线缆想象成一束线，含8条“频道线缆”。
不过，[致密线缆](../items-blocks-machines/cables.md#dense-cable) 可传递至多32个频道。
另一种，也是除此之外的唯二的可以传递32个频道的设备是<ItemLink id="me_p2p_tunnel" />和[量子桥](../items-blocks-machines/quantum_bridge.md)。
每当有设备用掉1个频道，把它想象成一束线中抽出一根USB“线缆”，显然地，这意味着该“线缆”在这根线的后续部分中不再可用。

<GameScene zoom="7" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_demonstration_1.snbt" />

  <LineAnnotation color="#33ff33" from="1 .4 .7" to="2.4 .4 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .7" to="2.4 .6 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .6" to="2.6 .4 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.4 .6 .7" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .4 .7" to="2.4 .4 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .6 .6" to="2.6 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 .6" to="2.6 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.1 .6 1.5" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 1.5" to="2.9 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.6 .6 1.5" to="2.6 .9 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .1 1.5" to="2.4 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .4" to="3.5 .6 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="3.5 .6 .4" to="3.5 .9 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="3.5 .1 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .3" to="1.5 .6 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1.5 .6 .3" to="1.5 .9 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1.5 .1 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#ff3333" from="3.5 .5 .5" to="5.5 .5 .5" alwaysOnTop={true}>
  线缆中全部8个频道都被用完了，因此驱动器没有分得频道。 
  </LineAnnotation>

  <LineAnnotation color="#993333" from="1 .5 .5" to="1.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="1.5 .5 .5" to="1.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2 .5 .5" to="2.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2.5 .5 .5" to="2.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="3 .5 .5" to="3.25 .5 .5" alwaysOnTop={true}/>

  <DiamondAnnotation pos="3.6 0.5 0.5" color="#ff0000">
        线缆中全部8个频道都被用完了，因此驱动器没有分得频道。
    </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

[智能线缆](../items-blocks-machines/cables.md)是你看到频道在网络中的路由情况的简易方式，它将显示频道的传递路径以及使用量。

频道每经过一个节点将耗能1/128 AE/t。这意味着向一个有着8设备以及超过96节点的网络中添加一个<ItemLink id="controller" />可能会降低网络的能耗，因为它改变了频道的分配方式

值得注意的是**频道和线缆颜色无关**。颜色仅仅是为了防止线缆相连的。

## 频道路由

使用<ItemLink id="controller" />时，频道分三步路由。
它们先通过相邻机器经最短路径前往[普通线缆](../items-blocks-machines/cables.md)(玻璃的、覆层的或智能的)；
然后它们经该普通线缆经最短路径前往[致密线缆](../items-blocks-machines/cables.md)(致密的或智能致密的)；
最后它们经该致密线缆经最短路径前往<ItemLink id="controller" />。
若最短路径以及被占满，部分[设备](devices.md)可能无法获得所需频道，使用染色线缆、线缆锚以及通道来确保
频道按照你希望的路径来路由。

例如，此例中部分驱动器无法分得频道，因为尽管线缆中频道承载量充足，但是频道试图按照最短路径路由，会使得部分线缆超载而部分线缆无频道经过。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 3.6" to="1.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.4 0.5 3.6" to="1.4 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 1.6" to="0.6 .5 1.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 1.6" to="0.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 3.4" to="1.4 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 3.4" to="1.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <BoxAnnotation color="#dddddd" min="1.2 0.2 3.2" max="1.8 0.8 3.8" alwaysOnTop={true} thickness="0.05">
        超过8个频道在路由时试图经过此处导致部分频道被截断。
  </BoxAnnotation>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

更仔细地制约频道的路径可以解决此问题。频道应当呈树状（或者叫刷子状），环和模糊不清的频道路径应极力避免。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue_fix.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 5.6" to="1 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

## 自组织网络

没有<ItemLink id="controller" />的网络会被认为是自组织的，至多可以承载8台使用频道的设备。
一旦超出上限，网络中使用频道的设备就会宕机。你可以移除一部分设备或是加入<ItemLink id="controller" />。

与带有控制器的网络不同，自组织网络中的[智能线缆](../items-blocks-machines/cables.md)会显示网络中频道的使用量而不仅仅是经过该线缆的频道量。

尽管自组织网络中也是每个设备使用1个频道，其路由方式与<ItemLink id="controller" />基于最短路径的频道分配方式大相径庭。

## 设计

正如上文[频道路由](channels.md#频道路由)中提到的，最好是设计一个树状网络，其中致密线缆从控制器处引出，然后普通线缆从致密线缆处引出，
最后[设备](../ae2-mechanics/devices.md)至多8个一组地接在普通线缆上。

以下是不该做的事情的例子：

按频道路径，

1. 向右离开控制器后，频道数立即被限制到了8，因为驱动器具有和普通线缆一致的行为，成为了传输的瓶颈。
然而由于我们没有使用智能线缆，无从得知多少频道正在被使用。剩余8频道。
1. 驱动器占用1频道。
剩余7频道。
1. 2频道向上进入终端。
剩余5频道。
1. 继续向右，接口占用了1频道.
剩余4频道。
1. 1频道向上进入样板供应器。
剩余3频道。
1. 继续向右，1频道向上进入输入总线。
剩余2频道。
1. 为分子组装室提供样板的供应器只分得2频道，因而有2个供应器未分得频道.

最终问题出在频道传输的瓶颈，以及缺乏对频道路由的充分思考。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/bad_network_structure.snbt" />

<LineAnnotation color="#33ff33" from="6.5 .5 1.5" to="6 .5 1.5" alwaysOnTop={true} thickness="0.4">
  32频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="6 .5 1.5" to="5.5 .5 1.5" alwaysOnTop={true} thickness="0.2">
  8频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 1.5 1.5" alwaysOnTop={true} thickness="0.1">
  2频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 1.5 1.5" to="5.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 2.5 1.5" to="5.5 2.5 1.1" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="4.5 .5 1.5" alwaysOnTop={true} thickness="0.158">
  5频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 1.5 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="3.5 .5 1.5" alwaysOnTop={true} thickness="0.122">
  3频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="3.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 2.5 1.5" to="3.7 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="1.5 .5 1.5" alwaysOnTop={true} thickness="0.1">
  2频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="1.5 0.3 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="0.5 0.5 1.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#33ff33" from="0.5 0.5 1.5" to="0.5 0.5 0.5" alwaysOnTop={true} thickness="0.071">
  1频道
</LineAnnotation>

<LineAnnotation color="#ff3333" from="0.5 1.5 1.5" to="0.5 1.3 1.5" alwaysOnTop={true} thickness="0.071">
  无频道
</LineAnnotation>

<LineAnnotation color="#ff3333" from="1.5 1.5 0.5" to="1.5 1.3 0.5" alwaysOnTop={true} thickness="0.071">
  无频道
</LineAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

---

这里有个不错的示范：

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="6.9 0 4.9" max="9.1 4 7.1" thickness="0.05">
        注意样板供应器是每8个一组的。
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 4 4" max="8 5 5" thickness="0.05">
        两个频道均占满的普通线缆汇集在一起，意味着你需要使用致密线缆。
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 0 13" max="8 1 14" thickness="0.05">
        不同颜色的线缆用于防止相邻线缆相连。
    </BoxAnnotation>


  <IsometricCamera yaw="315" pitch="30" />
</GameScene>

## 频道模式

基于Minecraft 1.18的AE2 10.0.0引入了改变AE2 频道行为的新选项。
通用部分的新配置项(`channel`)控制该选项，此外有一个新的游戏内命令让管理员们可以在游戏内改变模式和配置。
命令`/ae2 channelmode <mode>`用于改变模式，而`/ae2 channelmode`用于显示当前模式。
在游戏内改变模式会让所有网络立即重启并在新模式下运作

这重启并改进了Minecraft 1.12中曾有的选项，并为那些只是想要稍微轻松一点的游戏体验而非完全移除这一机制的玩家提供了更好的选项。

下表列出了配置文件和命令中所有支持的模式。

| 设置       | 描述                                                                                                                  |
| ---------- | -------------------------------------------------------------------------------------------------------------------- |
| `default`  | 默认模式，线缆和自组织网络的频道承载力如本教程所述。                                                                      |
| `x2`       | 所有频道的承载力翻一倍(普通线缆16，致密线缆64，自组织网络支持16频道)。                                                     |
| `x3`       | 所有频道的承载力翻两倍(普通线缆24，致密线缆96，自组织网络支持24频道)。                                                     |
| `x4`       | 所有频道的承载力翻三倍(普通线缆32，致密线缆128，自组织网络支持32频道)。                                                    |
| `infinite` | 所有频道的承载力不再受限。 控制器仍然会**大幅**降低网络能耗。智能线缆只会有完全关(未承载频道)和完全开(至少承载1个频道)两种状态。|