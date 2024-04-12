---
description: 程序包部署
---

# 二进制包部署

## 准备环境

* [x] 下载官方windows/linux系统安装包
* [x] 执行prometheus.exe/sh

## 默认配置

{% code fullWidth="false" %}
```
# my global config
global:
  scrape_interval: 15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
  evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
  # scrape_timeout is set to the global default (10s).

# Alertmanager configuration
alerting:
  alertmanagers:
    - static_configs:
        - targets:
          # - alertmanager:9093

# Load rules once and periodically evaluate them according to the global 'evaluation_interval'.
rule_files:
  # - "first_rules.yml"
  # - "second_rules.yml"

# A scrape configuration containing exactly one endpoint to scrape:
# Here it's Prometheus itself.
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: "prometheus"

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
      - targets: ["localhost:9090"]
```
{% endcode %}



1. 如果使用AlertManager通知功能，则取消注释`# - alertmanager:9093`、修改为自己的环境yourIP:9093
2. 如果使用告警规则功能，则填写`rule_files:`,可使用文件路径、"\*"等通配符，支持当前文件相对、绝对路径
3. 如果使用服务监控功能，则增加`scrape_configs:,`一个job为一个配置单元，targets为目标指标地址

