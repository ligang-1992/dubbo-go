# Apache Dubbo-go [English](./README.md) #

[![Build Status](https://travis-ci.org/apache/dubbo-go.svg?branch=master)](https://travis-ci.org/apache/dubbo-go)
[![codecov](https://codecov.io/gh/apache/dubbo-go/branch/master/graph/badge.svg)](https://codecov.io/gh/apache/dubbo-go)
[![go.dev reference](https://img.shields.io/badge/go.dev-reference-007d9c?logo=go&logoColor=white&style=flat-square)](https://pkg.go.dev/github.com/apache/dubbo-go?tab=doc)
[![Go Report Card](https://goreportcard.com/badge/github.com/apache/dubbo-go)](https://goreportcard.com/report/github.com/apache/dubbo-go)
![license](https://img.shields.io/badge/license-Apache--2.0-green.svg)

---
Apache Dubbo Go 语言实现

## 证书 ##

Apache License, Version 2.0

## 发布日志 ##

[v1.4.0 - 2020年3月17日](https://github.com/apache/dubbo-go/releases/tag/v1.4.0)

[v1.3.0 - 2020年3月1日](https://github.com/apache/dubbo-go/releases/tag/v1.3.0)

[v1.2.0 - 2019年11月15日](https://github.com/apache/dubbo-go/releases/tag/v1.2.0)

[v1.1.0 - 2019年9月7日 捐献给Apache之后的第一次release](https://github.com/apache/dubbo-go/releases/tag/v1.1.0)

[v1.0.0 - 2019年5月29日 兼容dubbo v2.6.5 版本](https://github.com/apache/dubbo-go/releases/tag/v1.0.0)

## 工程架构 ##

基于dubbo的extension模块和分层的代码设计(包括 protocol layer, registry layer, cluster layer, config 等等)。我们的目标是：你可以对这些分层接口进行新的实现，并通过调用 extension 模块的“ extension.SetXXX ”方法来覆盖 dubbo-go [同 go-for-apache-dubbo ]的默认实现，以完成自己的特殊需求而无需修改源代码。同时，欢迎你为社区贡献有用的拓展实现。

![框架设计](https://raw.githubusercontent.com/wiki/dubbo/dubbo-go/dubbo-go%E4%BB%A3%E7%A0%81%E5%88%86%E5%B1%82%E8%AE%BE%E8%AE%A1.png)

关于详细设计请阅读 [code layered design](https://github.com/apache/dubbo-go/wiki/dubbo-go-V1.0-design)

## 功能列表 ##

实现列表:

- 角色端
    * Consumer
    * Provider

- 传输协议
    * HTTP
    * TCP

- 序列化协议
    * JsonRPC V2
    * Hessian V2

- 协议
    * Dubbo
    * Jsonrpc2.0
    * [gRPC](https://github.com/apache/dubbo-go/pull/311)
    * [RESTful](https://github.com/apache/dubbo-go/pull/352)
    
- 路由器
    * [Condition router](https://github.com/apache/dubbo-go/pull/294)
    * [Health check router](https://github.com/apache/dubbo-go/pull/389)
    
- 注册中心
    * ZooKeeper
    * [etcd v3](https://github.com/apache/dubbo-go/pull/148)
    * [nacos](https://github.com/apache/dubbo-go/pull/151)
    * [consul](https://github.com/apache/dubbo-go/pull/121)
    * [k8s](https://github.com/apache/dubbo-go/pull/400)

- 动态配置中心与服务治理配置器
    * Zookeeper
    * [apollo](https://github.com/apache/dubbo-go/pull/250)
    * [nacos](https://github.com/apache/dubbo-go/pull/357)

- 集群策略
    * Failover
    * [Failfast](https://github.com/apache/dubbo-go/pull/140)
    * [Failsafe/Failback](https://github.com/apache/dubbo-go/pull/136)
    * [Available](https://github.com/apache/dubbo-go/pull/155)
    * [Broadcast](https://github.com/apache/dubbo-go/pull/158)
    * [Forking](https://github.com/apache/dubbo-go/pull/161)

- 负载均衡策略
    * Random
    * [RoundRobin](https://github.com/apache/dubbo-go/pull/66)
    * [LeastActive](https://github.com/apache/dubbo-go/pull/65)
    * [ConsistentHash](https://github.com/apache/dubbo-go/pull/261)

- 过滤器
    * Echo Health Check
    * [服务熔断&降级](https://github.com/apache/dubbo-go/pull/133)
    * [TokenFilter](https://github.com/apache/dubbo-go/pull/202)
    * [AccessLogFilter](https://github.com/apache/dubbo-go/pull/214)
    * [TpsLimitFilter](https://github.com/apache/dubbo-go/pull/237)
    * [ExecuteLimitFilter](https://github.com/apache/dubbo-go/pull/246)
    * [Auth/Sign](https://github.com/apache/dubbo-go/pull/323)
    * [Metrics filter](https://github.com/apache/dubbo-go/pull/342)
    * [Tracing filter](https://github.com/apache/dubbo-go/pull/335)

- 调用
    * [泛化调用](https://github.com/apache/dubbo-go/pull/122)
    
- 监控
    * Opentracing API
    * [Prometheus](https://github.com/apache/dubbo-go/pull/342)

- Tracing
    * [For jsonrpc](https://github.com/apache/dubbo-go/pull/335)
    * [For dubbo](https://github.com/apache/dubbo-go/pull/344)
    * [For grpc](https://github.com/apache/dubbo-go/pull/397)

- 其他功能支持:
    * 启动时检查
    * 服务直连
    * 多服务协议
    * 多注册中心
    * 多服务版本
    * 服务分组

开发中列表:

- 元数据中心 (dubbo v2.7.x)
- 服务发现 (dubbo v2.7.x)

你可以通过访问 [roadmap](https://github.com/apache/dubbo-go/wiki/Roadmap) 知道更多关于 dubbo-go 的信息。

![feature](./doc/pic/arch/dubbo-go-arch.png)

## 文档

https://dubbogo.github.io/dubbo-go-website (**完善中**)

## 快速开始 ##

[dubbo-samples/golang](https://github.com/dubbogo/dubbo-samples)这个项目的事例展示了如何使用 dubbo-go 。请仔细阅读 [dubbo-samples/golang/README.md](https://github.com/dubbogo/dubbo-samples/blob/master/golang/README.md) 学习如何处理配置并编译程序。

## 运行单测

### 准备

Mac/Linux
```bash
sh ./before_ut.sh
```

Windows
```bash
before_ut.bat
```

### 执行
```bash
go test ./...

# coverage
go test ./... -coverprofile=coverage.txt -covermode=atomic
```

## 编译

请移步 [dubbo-samples/golang](https://github.com/dubbogo/dubbo-samples)

## 如何贡献

如果您愿意给 [Apache/dubbo-go](https://github.com/apache/dubbo-go) 贡献代码或者文档，我们都热烈欢迎。具体请参考 [contribution intro](https://github.com/apache/dubbo-go/blob/master/contributing.md)。

## 性能测试 ##

性能测试项目是 [dubbo-go-benchmark](https://github.com/dubbogo/dubbo-go-benchmark)。

关于 dubbo-go 性能测试报告，请阅读 [dubbo benchmarking report](https://github.com/apache/dubbo-go/wiki/Benchmark-test-of-dubbo) & [jsonrpc benchmarking report](https://github.com/apache/dubbo-go/wiki/Benchmark-test-of-jsonrpc)。

## [User List](https://github.com/apache/dubbo-go/issues/2)

若你正在使用 [apache/dubbo-go](github.com/apache/dubbo-go) 且认为其有用或者向对其做改进，请忝列贵司信息于 [用户列表](https://github.com/apache/dubbo-go/issues/2)，以便我们知晓之。

<div>
<table>
  <tbody>
  <tr></tr>
    <tr>
      <td align="center"  valign="middle">
        <a href="" target="_blank">
          <img width="222px"  src="https://pic.c-ctrip.com/common/c_logo2013.png">
        </a>
      </td>
      <td align="center"  valign="middle">
        <a href="" target="_blank">
          <img width="222px"  src="https://user-images.githubusercontent.com/52339367/84628582-80512200-af1b-11ea-945a-c6b4b9ad31f2.png">
        </a>
      </td>
      <td align="center"  valign="middle">
        <a href="" target="_blank">
          <img width="222px"  src="https://mosn.io/images/community/tuya.png">
        </a>
      </td>
      <td align="center"  valign="middle">
        <a href="https://github.com/mosn" target="_blank">
          <img width="222px"  src="https://raw.githubusercontent.com/mosn/community/master/icons/png/mosn-labeled-horizontal.png">
        </a>
      </td>
    </tr>
    <tr></tr>
  </tbody>
</table>
</div>
