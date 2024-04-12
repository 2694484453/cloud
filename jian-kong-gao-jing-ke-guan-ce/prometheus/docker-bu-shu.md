---
description: 使用容器化部署
---

# Docker方式部署

## 准备环境

* [x] 已安装docker
* [x] 已安装docker-compose
* [x] 建议配置镜像加速地址

## docker compose安装脚本

{% code title="prometheus.yml" overflow="wrap" lineNumbers="true" fullWidth="false" %}
```yaml
version: "3"
services:
  prometheus:
    image: bitnami/prometheus:latest
    container_name: prometheus
    ports:
      - 9100:9100
      - 9090:9090
    volumes:
      - /data/prometheus/data:/opt/bitnami/prometheus/data
      - /data/prometheus/prometheus.yml:/opt/bitnami/prometheus/conf/prometheus.yml
      - /data/prometheus/conf.d:/opt/bitnami/prometheus/conf/conf.d
```
{% endcode %}

注：

```
/data/prometheus/prometheus.yml #配置文件
/data/prometheus/conf.d #服务发现文件，格式为json
/data/prometheus/data #数据持久化
```
