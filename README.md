#IRIS for Health  

Integrated hospital data extraction business solution based on IRIS for Health

Summary:  
With the continuous enrichment of hospital information construction content, more and more business coverage, the data requirements of related scientific research projects are also increasing, and the hospital has put forward new requirements for the data management of various business systems.Due to the diverse backgrounds of scientific research projects, the data models and data volumes in the requirements are also different, and the interface development, interface management and code maintenance of each system are becoming more and more complicated.To solve this dilemma, we used IRIS to integrate the hospital data extraction business solution.The application can be configured to realize the query business interface, greatly reducing the key operation cycle of development, maintenance, implementation and other projects.

Key Applications: Ensemble, SOAP API, ObjectScript, SQL, JDBC, XML Schema  

Technical details and application introduction:  
Technical details:  
Ensemble supports XML documents as virtual documents.A virtual document is a message that is partially integrated and parsed.This type of message has a standard integration header and standard message properties, such as ID, priority, and SESSIONID.However, the data in the message cannot be used as a message property;Instead, it is stored directly in the global variables used internally for faster processing.

XML Schema:  
The program has a DOCTYPE reference to the self-created XML Schema.  

Application link:  
https://github.com/D-red763/Ensemble/blob/main/XML%20Schema/TongjiExchange.xsd  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/ResponseDatasetMessage.xml  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/ResponseMessageHeader.xml  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/ResponseMessageBody.xml  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/Result.xml  

SQL access:  
Ensemble provides SQL access to data through ObjectScript, REST APIs, and JDBC.  

Application:  
In the data extraction business, companies only provided their own data sources, and then we used Ensemble built-in Adapter, SOAP API, and JDBC to implement SQL access to the data to establish the business interface.

Application link  
https://github.com/D-red763/Ensemble/blob/main/KY/Adapter/OutboundAdapterFix.xml

JDBC  
Link database through JDBC mode for data extraction.  

Soap API  
Application:  
The SOAP API provides a standard way for applications running on different operating systems and using different technologies and programming languages to communicate with each other.

Application link:  
https://github.com/D-red763/Ensemble/blob/main/KY/BS/KYQDService.xml

Using business processes:  
According to the element path of XML, the data extraction process can be configured by graphical tools.

Application link:  
https://github.com/D-red763/Ensemble/blob/main/KY/Rule/KYQDServiceRule.xml


Establish application cases

Application construction:  
Basic environment  
Ensemble Version Information: Ensemble-2017.2.2.865.0-Win_x64  
Ensemble has a Java, JDBC environment  
You can use SOAPUI for testing  
Installation steps  
① Establish a SOAP service  
Create a new Web application.  
This step can be seen in the image: 
Application running/Creating Web application.png  
(2) configure SQL - JDBC  
Create an SQL connection to the test database Oracle.  
③ Import XML Schema  
In Ensemble > XMLSchema, import XMLSchema file, build XML structure standard.  
④ Import code  
Import the code in KY, compile and open Production,  
Note: Modify BO configuration information (DNS), configure JavaGateWay, etc  
Application testing  
You can use the SOAPUI tool (other tools are also available) for testing and verification  
Application of summary  
This application takes the query of patient services as the case, and can carry out configuration rich implementation of inbound and outbound protocols, query conditions and business types to solve the query business interface problem.


# IRIS for Health
基于 IRIS for Health 整合医院数据提取业务解决方案  

概述：  
随着医院信息化建设内容不断丰富，业务面覆盖越来越广，相关科研项目的数据需求也越来越多，医院对各个业务系统的数据管理提出了新的要求。由于科研项目背景多样，需求中的数据模型以及数据体量也不尽相同，各个系统的接口开发、接口管理、代码维护工作也变得越来越繁杂。针对这一困境，我们采用Ensemble整合医院数据提取业务解决方案。该应用程序可通过配置完成查询业务接口实现，大大缩小开发、维护、实施等项目关键运转周期。  

关键应用： Ensemble、Soap API、ObjectScript、SQL、JDBC、XML Schema  

技术细则及应用介绍：  
技术细则  
Ensemble支持将XML文档作为虚拟文档。虚拟文档是一种仅部分集成解析的消息。这类消息具有标准的集成消息头和标准的消息属性，如ID、优先级和SessionId。然而，消息中的数据不能作为消息属性使用;相反，它直接存储在内部使用的全局变量中，以获得更快的处理速度。  

XML Schema  
程序中具有自建立XML Schema的DocType引用。  
应用链接  

https://github.com/D-red763/Ensemble/blob/main/XML%20Schema/TongjiExchange.xsd  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/ResponseDatasetMessage.xml  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/ResponseMessageHeader.xml  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/ResponseMessageBody.xml  
https://github.com/D-red763/Ensemble/blob/main/KY/MSG/Result.xml  


SQL访问  
Ensemble通过 ObjectScript、REST API及JDBC提供对数据的SQL访问.  
应用：  
在数据提取业务中，公司们只提供各自的数据源，之后我们采用Ensemble内置Adapter、Soap API及JDBC来实现对数据的SQL访问，来建立业务接口。  
应用链接 https://github.com/D-red763/Ensemble/blob/main/KY/Adapter/OutboundAdapterFix.xml  
JDBC  
通过JDBC方式链接数据库，进行数据提取。  

Soap API  
应用:  
SOAP API提供了一种标准的方法，使得运行在不同的操作系统并使用不同的技术和编程语言的应用程序可以互相进行通信。  
应用链接  
https://github.com/D-red763/Ensemble/blob/main/KY/BS/KYQDService.xml  

使用业务流程  
根据XML的元素路径进行取值，可利用图形化处理工具对数据提取过程进行配置管理。  
应用链接  
https://github.com/D-red763/Ensemble/blob/main/KY/Rule/KYQDServiceRule.xml  


建立应用案例  
应用搭建：  
基本环境  
Ensemble版本信息：ensemble-2017.2.2.865.0-win_x64  
Ensemble具有JAVA、JDBC环境  
可采用SoapUI进行测试  
安装步骤  
① 建立Soap服务  
新建Web应用程序。  
该步骤可见图片：应用程序运行情况/创建Web应用程序.png  
② 配置SQL-JDBC  
建立SQL连接，连接测试数据库Oracle。  
③ 导入XML Schema  
在Ensemble > XMLSchema ，导入XML Schema文件，自建XML结构标准。  
④ 导入代码  
导入KY中的代码，编译，打开Production,  
注意：修改BO配置信息（DNS）、配置JavaGateway等  

应用测试  
可采用SoapUI工具（其他工具也可以）进行测试验证  

应用总结  
本应用程序以查询患者服务为案例，可进行入站出站协议、查询条件、业务类型都可进行配置丰富实现，来解决查询业务接口问题。  
