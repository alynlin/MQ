MQ选型
====
## 一、MQ选型背景
为了满足业务场景需要了，性能瓶颈了，扩展性需要了等额巴拉巴拉的问题

## 二、MQ选型指标
### 2.1 需要考虑哪些指标
* 是够满足业务需要？
* 支持什么语言？
* 是否有监控？
* HA如何？是否支持failover？failover过程中是否会丢消息？
* 扩展性？
* 是否支持持久化？
* 是否支持有序消费？
* 是否支持延迟消息？
* 开发团队是否可以理解并修改源码？
* 社区是否活跃，响应是否迅速？
* 性能
### 2.2 指标对比
* 高可用
  * TIBCO支持主从，不支持集群
  * RabbitMQ集群化最方便，而且能动态配置，集群中所有节点拥有相同的元数据。所有client都与master进行通信，master将update同步给所有slave。slave过多会占用较多网络带宽
  * RocketMQ可以配置多Master，且每个Master可以配置一个Slave。如果一个Master挂掉，此Master对应Slave不会自动升级为Master但会继续提供读服务，写只能向其他Master写
* 扩展性
  * TIBCO扩展性较差，成为性能瓶颈
  * RabbitMQ集群化最方便
  * RocketMQ水平扩展方便，性能满足不了，直接加机器动态扩展
* 性能
性能虽然重要，但是不是最主要的考量指标，对于一般业务，性能不会成为瓶颈，性能满足不了时，可通过扩展来满足
  * 单点性能 ： RabbitMQ>TIBCO>RocketMQ
### 2.3 MQ 选择
  选择RocketMQ作为我们的开源替换方案

## 三、RocketMQ 概述
### 3.1 RocketMQ 概述
### 3.2 术语

## 四、bullet介绍（如何发布和订阅消息）
### 4.0 接入bullet准备工作
* 部署broker集群(公共部分使用架构组提供的broker集群)
* 申请创建topic
* 申请创建消费组
### 4.1 项目中如何引用bullet
### 4.2 如何使用bullet发布消息
### 4.3 如何使用bullet订阅消息
### 4.4 案列及注意点
### 4.5 消费幂等的必要性
### 4.6 如何发布上线，需要申请哪些资源
### 4.7 使用规范
* 命名规范
* 订阅一致性
* 消费幂等性
## 五、问答环节


