# IRIS for Health

Create a unified hospital data extraction scheme based on IRIS for Health  

Summary:  
With the continuous enrichment of hospital information construction content, more and more business coverage, the data requirements of related scientific research projects are also increasing, and the hospital has put forward new requirements for the data management of various business systems.Due to the diverse background of scientific research projects and the different data models in the requirements, the interface development, interface management and code maintenance of each system have become more and more complicated.In view of this dilemma, we use IRIS to create a unified hospital data extraction scheme.The application provides a common data extraction service (BS) that can be configured to achieve interface development (multiple BOs) for accessing multiple different data sources, greatly reducing development, maintenance, implementation, and other costs.  

Key Applications: IRIS, SOAP API, ObjectScript, SQL, JDBC, XML Schema  

Technical details and application introduction:  
Technical details  
IRIS supports XML documents as virtual documents.A virtual document is a message that is partially integrated and parsed.This type of message has a standard integration header and standard message properties, such as ID, priority, and SESSIONID.However, the data in the message cannot be used as a message property;Instead, it is stored directly in the global variables used internally for faster processing.  

XML Schema  
The program has a DOCTYPE reference to the self-created XML Schema.  
Application link  
https://github.com/D-red763/IRISApplication/blob/main/XML%20Schema/TongjiExchange.xsd  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/ResponseDatasetMessage.xml  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/ResponseMessageHeader.xml  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/ResponseMessageBody.xml  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/Result.xml  

SQL access  
Iris provides SQL access to data through ObjectScript, SOAP APIs, and JDBC.  
Application:  
In the data extraction business, companies only provided their own data sources, and then we used IRIS built-in Adapter, SOAP API, and JDBC to implement SQL access to the data to establish the business interface.  
Application link https://github.com/D-red763/IRISApplication/blob/main/KY/Adapter/OutboundAdapterFix.xml  
JDBC  
Link database through JDBC mode for data extraction. 

Soap API  
Application:  
The SOAP API provides a standard way for applications running on different operating systems and using different technologies and programming languages to communicate with each other.  
Application link  
https://github.com/D-red763/IRISApplication/blob/main/KY/BS/KYQDService.xml  

Using business processes  
According to the element path of XML, the data extraction process can be configured by graphical tools.  
Application link  
https://github.com/D-red763/IRISApplication/blob/main/KY/Rule/KYQDServiceRule.xml  

Establish application cases  
Application construction:  
Basic environment  
Iris version information: IRIS_Community-2020.1.0.215.0-win_x64   
And has Java, JDBC environment  

IRIS installation:  
① Configure IIS:  
https://github.com/D-red763/IRISApplication/tree/main/Config%20IIS%20and%20Website  
② Instance installation:  
https://github.com/D-red763/IRISApplication/tree/main/Instance%20installation  
③ Configure Namespace:  
https://github.com/D-red763/IRISApplication/tree/main/Config%20Namespace  

Installation steps  
① Establish a SOAP service  
Create a new Web application.  
This step can be seen in the image:   
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/JDBC%20installation.png  
(2) configure SQL - JDBC  
Create an SQL connection to the test database Oracle.  
③ Import XML Schema  
In  Interoperability > XMLSchema, import XMLSchema file, build XML structure standard.  
④ Import code  
Import the code in KY, compile and open Production,  
Note: Modify BO configuration information (DNS), configure JavaGateWay, etc  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/JDBC%20installation.png  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/JavaGateway.png  

Application testing  
You can use the SOAPUI tool (other tools are also available) for testing and verification  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/SoapUITesting.png  

Application of summary  
This application takes XML Schema as the message carrier, combined with the built-in XML parsing tool of IRIS, can manage the configuration of multiple data sources (BO) through one service (BS) and one set of codes, and solve the problem of data extraction from different sources.  


# IRIS for Health
基于 IRIS for Health 创建医院数据统一提取方案  

概述：  
随着医院信息化建设内容不断丰富，业务面覆盖越来越广，相关科研项目的数据需求也越来越多，医院对各个业务系统的数据管理提出了新的要求。由于科研项目背景多样，需求中的数据模型也不尽相同，各个系统的接口开发、接口管理、代码维护工作也变得越来越繁杂。针对这一困境，我们采用IRIS创建医院数据统一提取方案 。该应用程序提供一个公共的数据提取服务（BS），可通过配置完成获取多个不同数据源的接口开发（多个BO），大大缩小开发、维护、实施等成本。  

关键应用： IRIS、Soap API、ObjectScript、SQL、JDBC、XML Schema  

技术细则及应用介绍：  
技术细则  
IRIS支持将XML文档作为虚拟文档。虚拟文档是一种仅部分集成解析的消息。这类消息具有标准的集成消息头和标准的消息属性，如ID、优先级和SessionId。然而，消息中的数据不能作为消息属性使用;相反，它直接存储在内部使用的全局变量中，以获得更快的处理速度。  

XML Schema  
程序中具有自建立XML Schema的DocType引用。  
应用链接  
https://github.com/D-red763/IRISApplication/blob/main/XML%20Schema/TongjiExchange.xsd  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/ResponseDatasetMessage.xml  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/ResponseMessageHeader.xml  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/ResponseMessageBody.xml  
https://github.com/D-red763/IRISApplication/blob/main/KY/MSG/Result.xml  


SQL访问  
IRIS通过 ObjectScript、SOAP API及JDBC提供对数据的SQL访问.  
应用：  
在数据提取业务中，公司们只提供各自的数据源，之后我们采用IRIS内置Adapter、Soap API及JDBC来实现对数据的SQL访问，来建立业务接口。  
应用链接 https://github.com/D-red763/IRISApplication/blob/main/KY/Adapter/OutboundAdapterFix.xml  
JDBC  
通过JDBC方式链接数据库，进行数据提取。  

Soap API  
应用:  
SOAP API提供了一种标准的方法，使得运行在不同的操作系统并使用不同的技术和编程语言的应用程序可以互相进行通信。  
应用链接  
https://github.com/D-red763/IRISApplication/blob/main/KY/BS/KYQDService.xml  

使用业务流程  
根据XML的元素路径进行取值，可利用图形化处理工具对数据提取过程进行配置管理。  
应用链接  
https://github.com/D-red763/IRISApplication/blob/main/KY/Rule/KYQDServiceRule.xml  


建立应用案例  
应用搭建：  
基本环境  
IRIS版本信息：IRIS_Community-2020.1.0.215.0-win_x64 
且具有JAVA、JDBC环境  

程序安装：  
①配置IIS：  
https://github.com/D-red763/IRISApplication/tree/main/Config%20IIS%20and%20Website  
②实例安装：  
https://github.com/D-red763/IRISApplication/tree/main/Instance%20installation  
③配置Namespace：  
https://github.com/D-red763/IRISApplication/tree/main/Config%20Namespace  

应用步骤  
① 建立Soap服务  
新建Web应用程序。  
该步骤可见图片：  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/JDBC%20installation.png  
② 配置SQL-JDBC  
建立SQL连接，连接测试数据库Oracle。  
③ 导入XML Schema  
在 Interoperability > XMLSchema ，导入XML Schema文件，自建XML结构标准。  
④ 导入代码  
导入KY中的代码，编译，打开Production,  
注意：修改BO配置信息（DNS）、配置JavaGateway等  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/JDBC%20installation.png  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/JavaGateway.png  

应用测试  
可采用SoapUI工具（其他工具也可以）进行测试验证  
https://github.com/D-red763/IRISApplication/blob/main/Application%20health/SoapUITesting.png  

应用总结  
本应用程序以XML Schema为消息载体，结合IRIS内置的XML解析工具，可通过一个服务（BS）、一套代码对多个数据源（BO）进行配置管理，来解决不同来源数据的提取问题。  
