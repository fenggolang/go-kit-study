#### go-kit架构分层
- Transport层: 主要负责与传输协议HTTP、gRPC、Thrift等相关的逻辑
- Endpoint层: 主要负责request/response格式的转换，以及公用拦截器相关的逻辑
- Service层: 主要专注于业务逻辑