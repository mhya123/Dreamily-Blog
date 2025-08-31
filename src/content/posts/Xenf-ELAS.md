---
title: Xenforo配置增强搜索
published: 2025-09-01
pinned: false
description: Xenforo论坛配置增强搜索.
tags: [Xenforo,Elasticsearch]
category: New
draft: false
---
# Elasticsearch Ubuntu 22 安装指南

本文将指导您在 Ubuntu 22+ 上安装和配置 Elasticsearch。

## 前置条件
- 一台运行 Ubuntu 22+ 的服务器
- 拥有 sudo 权限的用户

## 安装步骤

### 1. 更新系统
首先，确保系统软件包是最新的：
```bash
sudo apt update && sudo apt upgrade -y
```
### 2. 安装 Java
Elasticsearch 需要 Java 环境。安装 OpenJDK：
```bash
sudo apt install openjdk-11-jdk -y
```
验证 Java 安装：
```bash
java -version
```

### 3. 添加 Elasticsearch 仓库
导入 Elasticsearch 的 GPG 密钥：
```bash
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
```
添加 Elasticsearch 仓库：
```bash
echo "deb https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-8.x.list
```

### 4. 安装 Elasticsearch
更新软件包列表并安装 Elasticsearch：
```bash
sudo apt update
sudo apt install elasticsearch -y
```

### 5. 配置 Elasticsearch
编辑配置文件 `/etc/elasticsearch/elasticsearch.yml`：
```bash
sudo nano /etc/elasticsearch/elasticsearch.yml
```
根据需要修改以下内容：
```yaml
network.host: 0.0.0.0
http.port: 9200
```

### 6. 启动和启用服务
启动 Elasticsearch 服务：
```bash
sudo systemctl start elasticsearch
```
设置开机自启：
```bash
sudo systemctl enable elasticsearch
```

### 7. 验证安装
检查 Elasticsearch 是否运行：
```bash
curl -X GET "localhost:9200"
```
---
## Xenforo配置相关插件

### 重要的一点！！
```bash
在选择增强搜索插件时一定要确定好自己的论坛所用xenforo版本
2.1，2.2，2.3 都不建议串用插件
```
## 后台设置
先进入 https://你的域名/admin.php?enhanced-search/indexes 对你的配置进行修改
![QQ20250901-010256](https://image.fkme.cyou/i/2025/09/01/1pd9k7.png)
再来到重建缓存重建搜索索引 https://你的域名/admin.php?tools/rebuild 
![QQ20250901-010408](https://image.fkme.cyou/i/2025/09/01/1q0m1d.png)
### 安装上面操作也就安装好了