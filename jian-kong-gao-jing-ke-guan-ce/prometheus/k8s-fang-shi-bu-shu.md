---
description: 容器编排部署
---

# 云原生部署

## 准备环境

* [x] Minikube
* [x] 安装helm
* [x] 下载tgz包/配置仓库地址



## 下载chart安装包

[https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack](https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack)

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## 按照提示执行命令

```sh
// 执行添加仓库
helm install my-kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 58.1.0
```

```
// 执行安装，可能提示更新仓库
helm install kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 58.1.0 -n monitor
```

## 检查是否成功创建资源

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
