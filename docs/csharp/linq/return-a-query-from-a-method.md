---
title: "从方法中返回查询"
description: "如何返回查询。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>如何：从方法中返回查询（C# 编程指南）
此示例演示如何以返回值和 `out` 参数形式从方法中返回查询。  
  
 查询对象可编写，这意味着你可以从方法中返回查询。 表示查询的对象不会存储生成的集合，而会根据需要存储生成结果的步骤。 从方法中返回查询对象的好处是可以进一步编写或修改这些对象。 因此，返回查询的方法的任何返回值或 `out` 输出参数也必须具有该类型。 如果某个方法可将查询具体化为具体的 <xref:System.Collections.Generic.List%601> 或 <xref:System.Array> 类型，则认为该方法在返回查询结果（而不是查询本身）。 仍然能够编写或修改从方法中返回的查询变量。  
  
## <a name="example"></a>示例  
 在下面的示例中，第一个方法以返回值的形式返回查询，第二个方法以 `out` 参数的形式返回查询。 请注意，在这两种情况下，返回的都是查询，而不是查询结果。  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>另请参阅  
 [LINQ 查询表达式](index.md)
