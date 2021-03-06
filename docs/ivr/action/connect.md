# 连接
<!-- toc -->

## connect 节点

```
connect
```

用于连接非自动连接的拨号

## 属性

| 参数                  | 说明                                      |
| --------------------- |  ---------------------------------------- |
| `max_duration`        | 最大连接时间（秒）                        |
| `mode`                | 连接模式 。参见[连接模式列表](#连接模式列表)               |
| `recording`           | 最大拨号等待时间（秒）                         |
| `volume1`             | 双通道连接建立后的第一方音量。 |  
| `volume1`             | 双通道连接建立后的第二方音量。 |  
| `play_time`           | 本次连接通话进行到这个时间点播放声音。 |
 
### 参数详情
####连接模式列表
| 枚举值                  | 说明                                      |
| --------------------- |  ---------------------------------------- |
| `1`        | 连接双方均可互相听到                                   |
| `2`        | 仅连接的第二方可以听到第一方;第一方听不到第二方        |
| `3`        | 仅连接的第一方可以听到第二方;第二方听不到第一方        |

## 内容
无

参数                  | 说明                                     
--------------------- | -----------------------------------------
`type`                | 同一个 IVR Response 中，动作节点的标签名称
`error`               | 如果 IVR 执行错误，将输出错误描述；如果没有错误，平台不会提供该参数

## 嵌套
`play`

**NOTE** 重复参数有效

## 示例

```xml
<response>
    <dial from="4001546646464">
        <number>13692208888</number>
        <connect max_duration="50">
            <play repeat="3">warning.wav</play>
        </connect>
    </dial>
    <next>http://yourhost/nextstep</next>   
</response>
```

## 事件

见 [IVR 事件](../evt/ivr/index.md)