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
git clone https://github.com/nirvana-lab/nirvana-ui.git
docker build . -t nirvana-ui:latest
```
- Service  
```
git clone https://github.com/nirvana-lab/nirvana7.git
docker build . -t nirvana-server:latest 
```      
   

### 2.部署

- 目录结构
```  
.
├── docker-compose.yaml
├── nirvana_pgdata  用来挂载pg的数据
└── script   用来挂载python脚本
```

- docker-compose.yaml  
```  
xdd
```

### 3.初始化GitLab Applications

登录GitLab，Setting-》Applications:  
`Name` 自定义名字  
`Redirect URI` Nirvana UI的地址    
`Scopes` 勾选api、read_user、read_api、read_repository、openid、profile、email    

![Tracker](/images/gitlab.png)

创建完成获得Application ID, Secret, Callback URL用于发送post请求
```
curl --location --request PUT 'http://{nirvana_ui_url}/api/sso'
	--header 'Content-Type: application/json'
	--data-raw '{
	"id": {Application ID},
	"secret": {Secret},
	"callback": {Callback URL}
	}'

```


如果没有gitlab请自行安装「[安装指南](https://github.com/lunamagic1978/document/blob/master/middleware/GitLab-ce%E5%AE%89%E8%A3%85.md)」

