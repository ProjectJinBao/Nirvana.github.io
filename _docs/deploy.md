---
title: 安装部署
category: Nirvana
order: 5
---

## 运行环境
Nirvana 是一个基于 Python 开发的测试框架，可以运行在 macOS、Linux、Windows 系统平台上。  


**Python 版本**：支持 Python 3.7及以上的所有版本。

**操作系统**：推荐使用 macOS/Linux。

## 安装

### 1.构建镜像
- UI  
```
git clone https://github.com/nirvana-lab/gittest.git
docker build . -t nirvana-ui:latest
```
- Service

```
git clone https://github.com/nirvana-lab/nirvana7.git
docker build . -t nirvana-server:latest 
```      
   

### 2.部署准备
在放置docker-compose.yaml的目录下创建以下目录：
.
├── docker-compose.yaml
├── nirvana_pgdata  这个目录是用来挂在pg的数据的
└── script   这个目录是用来挂在python脚本的

