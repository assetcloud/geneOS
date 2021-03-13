# 面向组织的云原生应用管理平台

> 平台主要面向组织用户，因此上架平台的应用应以组织为颗粒度设计多租户。用户从属于组织，组织可设置内设机构和岗位，用户可以加入多组织，组织之间可以组合成集团。 传统SaaS应用提供服务，组织或用户需要登陆服务地址，注册账号，提供相关用户认证信息。云原生应用平台要求面向组织和用户聚合服务。SaaS应用必须注册到平台，用户登陆平台，即可获取和使用SaaS服务。

## 设计理念
平台以组织用户为中心，利用云原生技术提升组织对应用和数据的管理能力，降低用户对技术心智负担。通过更细颗粒度的划分服务边界，明晰权责利关系。改变软件交付和分发方式以及数据资产的管理方式。充分释放云计算的技术红利，让开发用户更专注核心业务的代码，为组织用户业务变革和价值创造提供持续的推动力。

## 平台目标
平台基于基于云原生技术架构原则和设计模式，旨在将云应用中的非业务代码部分进行最大化的剥离，从而让云设施接管应用中原有的大量非功能特性（如弹性、韧性、安全、可观测性、灰度等），使业务不再有非功能性业务中断困扰的同时，具备轻量、敏捷、高度自动化的特点。

云原生应用平台通过定义开放标准，向下封装基础设施资源，屏蔽底层架构的差异性，向上支撑多种工作负载和分布式架构。提供应用全生命周期管理、运维管理、配置范围和扩展和管理、以及语言无关的编程框架，一起构成了崭新的应用与云之间的编程界面。把应用中和业务无关的逻辑和职责，剥离到云服务，并通过实践达成共识标准，让应用开发者能够在专有云、公有云、或者混合云的场景中，都能有一致的研发运维体验。

## 平台能力
平台聚焦组织核心业务，围绕用户做聚合服务。充分利用以Kubernetes为核心的云原生生态优势，向上支持众多开源主流框架构建微服务、数据库、消息中间件、大数据、AI、区块链等各种类型应用。从无状态应用、到各类组织核心应用、再到数字化、智能化、智慧化应用，组织机构和开发者都可以基于Kubernetes顺利地自动部署、扩展和管理容器化应用。

>平台主要聚焦以下四个方面能力：

1. **应用管理**    
提供应用开发、部署、迭代、运维、运营能力。利用各类公共组件，敏捷开发环境，快速搭建应用。提供从代码到镜像到部署的流水线支持，通过持续集成和持续部署，进行快速迭代。提供的组件、接口、服务和应用的各种颗粒度运维和运营能力。利用市场机制，提供应用上架、发布、下架、工单等运营工具满足基本商业化运营需求。

1. **组织管理**   
提供灵活的组织管理。根据业务场景自由创建组织树。能够实现组织树继承、复制、迁移、拆分、合并等操作，满足各类跨地区、跨层级、跨部门的针对组织树的应用分发、流程设计。更够对接各类基于组织树的用户验证和鉴权，消息分发，数据操作等复杂组织管理需求。

1. **数据管理**   
提供数据分析、建模能力,专注业务层数据服务能力。利用消息机制，实现元数据、字典等数据标准的维护、发布等管理，在应用设计和建模阶段介入对数据的管理，实现数据规范的前对齐。拥有完善的数据治理能力，能够平滑对接各类开放域或私有域的基础数据平台，公共数据服务平台。实现对数据资产细颗粒度的保护，输出各类场景数据服务，支持应用迭代和创新需求。

1. **资源管理**   
在网络联通的条件下，屏蔽基础资源的差异，实现平台和底层资源解藕，利用云原生技术，对接虚拟计算资源、容器平台、云存储资源、区块链、物联网等各类基础云服务平台，实现跨云资源适配和管理能力，统一向应用层输出基础能力。


## 参与项目
> 本项目利用开源项目go-zero搭建，在正式进入实际开发之前，需要做一些准备工作，比如：Go环境的安装，grpc代码生成使用的工具安装， 必备工具Goctl的安装，Golang环境配置等,熟悉go-zero中的编码规范

### 前端利用现有云原生应用管理平台前端
https://www.assetcloud.org.cn

### 开发流程

#### goctl环境准备[1]
#### 数据库设计 参考assetcloud平台项目数据库设计
#### 业务开发
#### 创建服务类型（api/rpc/rmq/job/script）
#### 编写api、proto文件 参考现有assetx后台api文档
#### 代码生成
#### 生成数据库访问层代码model 以现有数据表生成对应文件
#### 配置config，yaml变更
#### 资源依赖填（ServiceContext）
#### 添加中间件
#### 业务代码填充
#### 错误处理

>项目进展随时同步在本文档。

#### 启动服务
etc/user-api.yaml文件中配置好数据库，在user目录下面执行
```
go run cmd/api/user.go -f cmd/api/etc/user-api.yaml
```