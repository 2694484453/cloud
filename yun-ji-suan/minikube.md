---
description: 如何安装一个minikube！
---

# 🏰 Minikube

## 准备环境

* [x] linux/windows机器
* [x] 安装docker
* [x] 配置docker镜像加速

## 下载安装包

[https://github.com/kubernetes/minikube](https://github.com/kubernetes/minikube)

根据自己的系统选择需要安装的版本

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## 添加命令到/usr/bin

<pre><code>// 修改文件必要的执行权限
<strong>mv minikube-xxx-xxx minikube &#x26;&#x26; chmod +x minikube
</strong></code></pre>

```
// 添加到/usr/bin
ln -s /data/minikube /usr/bin/minikube
```

```
// 是否成功
minikube version
```

## 创建预设资源

cd  /$home下，一般为/root

```
// 创建文件夹
mkdir .minikube && cd .minikube
```

```
// 创建文件夹
mkdir config && cd config
```

```
// 创建资源文件json
touch config.json
```

```
// 写入以下内容,核心、内存、版本
{
  "cpus": 4,
  "memory": "8192",
  "driver": "docker",
  "kubernetes-version": "v1.27.3"
}
```

## 执行创建

```
// linux下执行
minikube start --force
```

```
// win下执行
minikube start
```

## 开启访问面板

等待镜像拉取成功后，启动消息执行完成 Done!

```
// 启用面板
minikube dashboard 
```

```
// 执行代理转发
nohup kubectl proxy --port=8002 --address='0.0.0.0' --accept-hosts='^.*' &
```

```
// 替换url，将127.0.0.1:xxx部分替换为ip:8002,其余不变

```

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
