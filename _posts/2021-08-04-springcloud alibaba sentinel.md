---
title: 'springcloud alibaba sentinel'
layout: post
tags:
  - sentinel
category: springcloud
---
springcloud alibaba sentinel。

<!--more-->

# 一、docker安装

```shell
docker pull bladex/sentinel-dashboard

docker run --name sentinel -d  -p 8858:8858  bladex/sentinel-dashboard
```

访问http://localhost:8858/即可

## 注：用docker部署的sentinel需要在yml配置client-ip:本地ip才行

```yaml
spring:
  application:
    name: cloudalibaba-sentinel-service
  cloud:
    nacos:
      discovery:
        # Nacos服务注册中心地址
        server-addr: localhost:8848
    sentinel:
      transport:
        # sentinel dashboard 地址
        dashboard: localhost:8858
        # 默认为8719，如果被占用会自动+1，直到找到为止
        port: 8719
        # 本地机器ip
        client-ip: 本机ip
```
