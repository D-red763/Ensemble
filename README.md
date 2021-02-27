# Ensemble
基于Ensemble整合医院数据提取业务解决方案

概述：
随着医院信息化建设内容不断丰富，业务面覆盖越来越广，相关科研项目的数据需求也越来越多，医院对各个业务系统的数据管理提出了新的要求。由于科研项目背景多样，需求中的数据模型也不尽相同，各个系统的接口开发、接口管理、代码维护工作也变得越来越繁杂。针对这一困境，我们采用Ensemble整合医院数据提取业务解决方案。该应用程序可通过配置完成查询业务接口实现，大大缩小开发、维护、实施等项目关键运转周期。

关键应用： Ensemble、Soap API、ObjectScript、SQL、JDBC、XML Schema

技术细则及应用介绍：
技术细则
Globals (key-value)
Globals是可以在IRIS数据库中存储和管理的稀疏多维数组。您可以使用ObjectScript和本机API处理Globals。
工具:
https://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=GGBL_MANAGING
应用：
应用程序根据Globals的键值对、访问速度快的特性。应用在本次程序的Rest分派类与BP流程管理中取值应用，解决了频繁取值速度慢、实现在查找表前端页面配置操作，如：存储了SQL模型、服务配置信息等等。
应用链接 https://github.com/ZBT-95/-IRIS-/blob/main/Application/Rest/Handler.cls
https://github.com/ZBT-95/-IRIS-/blob/main/Application/BP/QueryManage.cls
SQL访问
InterSystems IRIS通过 ObjectScript、REST API及JDBC提供对数据的SQL访问.
工具:
https://docs.intersystems.com/irislatest/csp/docbook/Doc.View.cls?KEY=GSQL_smp
应用：
在查询业务中，三方系统不配合接口改造，导致接口实现困难问题。此时，我们采用IRIS内嵌模型ObjectScript、REST API及JDBC来实现对数据的SQL访问，来建立业务接口。
应用链接 https://github.com/ZBT-95/-IRIS-/blob/main/Application/SQL/BO/Query.cls
Object访问
通过ObjectScript、REST API，InterSystems IRIS提供了在Globals 存储和更改对象实例的途径。
文档：
https://docs.intersystems.com/irislatest/csp/docbook/Doc.View.cls?KEY=PAGE_multimodel_object
应用：
在整个交互过程中，直接操纵InterSystems IRIS对象。ObjectScript类定义通常用作创建对象（例如患者，科室或医护人员）的模板。
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/Dept.cls https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/Doctor.cls https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/Patient.cls https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/QueryMsg.cls https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/SQLMessage.cls
Rest API
应用:
REST是一种架构风格，而不是一种明确定义的格式。它是面向资源的。通常，资源由URL标识，并显式使用基于HTTP方法的操作，例如GET，POST，PUT和DELETE。
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/Rest/Handler.cls
使用业务流程BPL
运用业务流程处理消息查询模型及对应SQL执行，可利用图形化处理业务消息。
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/BP/QueryManage.cls
JDBC
通过JDBC方式链接数据库，进行查询业务消息。
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/SQL/BO/Query.cls


互操作性适配器
利用SQL、SOAP等入站出站适配器完成应用程序业务消息交互。
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/SOAP/BS/QueryService.cls
https://github.com/ZBT-95/-IRIS-/blob/main/Application/SQL/BO/Query.cls
工作流程引擎
利用Production来详细说明业务流程，保证业务消息规范交互。
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/PD/QueryProduction.cls

Model
程序中具有自建立模型引用.比如：患者、医护、科室模型
应用链接
https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/Dept.cls
https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/Doctor.cls
https://github.com/ZBT-95/-IRIS-/blob/main/Application/MSG/Patient.cls
建立应用案例（此应用程序以患者为例）
应用搭建：
基本环境
IRIS版本信息：IRIS for Windows (x86-64) 2020.1 (Build 215U) Mon Mar 30 2020 20:14:33 EDT [HealthConnect:2.1.0]
IRIS具有JAVA、JDBC环境
可采用PostMan进行测试
安装步骤
① 建立Rest服务
新建Web应用程序→配置分派类→配置权限。
该步骤可见图片：应用程序运行情况/webaplication(Query).png及webaplication(role).png
② 配置SQL-JDBC
建立SQL连接，连接测试数据库Mysql，导入测试jhip_patient_info.sql
③ 配置查找表
Global-^Ens.LookupTable中查找表文件导入
④ 导入代码
导入ApplicationCode中的代码，编译，打开Production,
注意：修改BO配置信息（DNS）、配置JavaGateway等
应用流程
略（见PDF）
应用测试
可采用Postman工具（其他工具也可以）进行测试验证
Postman可导入Query.postman_collection.json，更改IP、端口号信息、URL进行测试。
应用总结
本应用程序以查询患者服务为案例，可进行入站出站协议、查询条件、业务类型都可进行配置丰富实现，来解决查询业务接口问题。
