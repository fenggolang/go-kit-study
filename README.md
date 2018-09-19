#### go-kit介绍
    go-kit本身不是一个框架，而是一套微服务工具集, 它可以用来解决分布式系统开发中的大多数常见问题. 所以你可以专注于你的业务逻辑中.

#### go-kit架构分层
- Transport层: 主要负责与传输协议HTTP、gRPC、Thrift等相关的逻辑
- Endpoint层: 主要负责request/response格式的转换，以及公用拦截器相关的逻辑,如log,metric,
            tracing,circuibreaker(断路器),rate-limiter(限流器)等，来保障业务系统的可用性。它们
            在设计上有一个共同特点：都是同传输协议无关的。在之前的一些http框架中，这些拦截器同传
            输协议是紧紧耦合在一起的，如果，此时我需要将某些HTTP接口改造成gRPC协议的接口，那么这
            些拦截器我还得再基于grpc再实现一遍，设计上存在一定的冗余。因此，借助go-kit这套工具集，
            我们就能很好的对transport协议，middleware进行扩展，且不会影响到业务本身的设计。
            你如果哪天因为某种原因，不想再继续使用go-kit这套东西，直接將Endpoint层和Transport层移除即可。                                                                                      
- Service层: 主要专注于业务逻辑
##### Transport层介绍
```markdown
transport属于数据传输层，比如使用HTTP、gRPC等协议进行数据的传输，负责数据的序列化和反序列化
```
##### Endpoint层介绍
```markdown
endpoint属于
```
##### Service层介绍
```markdown

```
---

#### 微服务架构设计点
- Rate Limiter 限流器

- Trasport 数据传输(序列化和反序列化)

- Logging 日志

- Metrics 指标

- Circuit breaker 断路器

- Request tracing 请求追踪

- Service Discovery 服务发现