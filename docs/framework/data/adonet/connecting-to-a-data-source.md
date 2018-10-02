---
title: 连接到 ADO.NET 中的数据源
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: f5788b9b0b19f32d03c917575db7b3f40324c0a2
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964574"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>连接到 ADO.NET 中的数据源
在 ADO.NET 中，使用**连接**对象以连接到特定的数据源，通过提供必要的身份验证连接字符串中的信息。 **连接**您使用的对象取决于数据源的类型。  
  
 随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。  
  
## <a name="in-this-section"></a>本节内容  
 [建立连接](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 介绍如何使用**连接**对象建立与数据源的连接。  
  
 [连接事件](../../../../docs/framework/data/adonet/connection-events.md)  
 介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。  
  
## <a name="see-also"></a>请参阅  
 [连接字符串](../../../../docs/framework/data/adonet/connection-strings.md)  
 [连接池](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapters 和 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [事务和并发性](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
