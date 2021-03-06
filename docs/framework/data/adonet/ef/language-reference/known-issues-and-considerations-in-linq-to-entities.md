---
title: "LINQ to Entities 中的已知问题和注意事项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dd45bc4f2229237c50e9bfda36e5fb18512f9ef0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>LINQ to Entities 中的已知问题和注意事项
本节提供有关 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 查询的已知问题的信息。  
  
-   [不能缓存的 LINQ 查询](#LINQQueriesThatAreNotCached)  
  
-   [排序信息丢失](#OrderingInfoLost)  
  
-   [不支持的无符号的整数](#UnsignedIntsUnsupported)  
  
-   [类型转换错误](#TypeConversionErrors)  
  
-   [不支持引用非标量变量](#RefNonScalarClosures)  
  
-   [嵌套的查询可能会失败，SQL Server 2000](#NestedQueriesSQL2000)  
  
-   [投影到匿名类型](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a>不能缓存的 LINQ 查询  
 从 .NET Framework 4.5 开始，LINQ to Entities 查询是自动缓存的。 但是，不自动缓存将 `Enumerable.Contains` 运算符应用到内存中集合的 LINQ to Entities 查询。 此外，不允许在已编译的 LINQ 查询中参数化内存中的集合。  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a>排序信息丢失  
 如果将列投影到匿名类型，则会导致对兼容级别设置为“80”的 [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] 数据库所执行的某些查询中会丢失排序信息。  当 order-by 列表中的列名与选择器中的列名相同时，就会发生这种情况，如下面的示例所示：  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a>不支持无符号整数  
 由于 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 不支持无符号整数，因此不支持在 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 查询中指定无符号整数类型。 如果指定无符号的整数<xref:System.ArgumentException>下面的示例中所示将查询表达式转换，期间引发异常。 此示例查询其 ID 为 48000 的订单。  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a>类型转换错误  
 在 Visual Basic 中，如果使用 `CByte` 函数将某一属性映射到值为 1 且为 SQL Server 位类型的列，则会引发 <xref:System.Data.SqlClient.SqlException> 并显示“发生算术溢出错误”消息。 下面的示例查询 AdventureWorks 示例数据库中的 `Product.MakeFlag` 列，在循环访问查询结果时引发一个异常。  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a>不支持引用非标量变量  
 不支持在查询中引用非标量变量（如实体）。 在此类查询执行时，会引发 <xref:System.NotSupportedException> 异常，并显示以下消息：“无法创建类型为‘`EntityType`’的常量值。 此上下文中仅支持基元类型(‘如 Int32、String 和 Guid’)。”[Unable to create a constant value of type 'Closure type'. Only primitive types ('such as Int32, String, and Guid') are supported in this context.]  
  
> [!NOTE]
>  支持引用标量变量的集合。  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a>使用 SQL Server 2000，嵌套查询可能会失败  
 使用 SQL Server 2000，如果 LINQ to Entities 查询生成具有三级或以上深度的嵌套 Transact-SQL 查询，则它们可能会失败。  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a>投影到匿名类型  
 如果通过使用 <xref:System.Data.Objects.ObjectQuery%601.Include%2A> 上的 <xref:System.Data.Objects.ObjectQuery%601> 方法将初始查询路径定义为包括相关对象，然后使用 LINQ 将返回的对象投影到匿名类型，则查询结果中将不包含在 Include 方法中指定的对象。  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 若要获取相关对象，请勿将返回的类型投影到匿名类型。  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a>请参阅  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
