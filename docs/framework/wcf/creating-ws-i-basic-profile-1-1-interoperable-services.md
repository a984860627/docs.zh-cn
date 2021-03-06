---
title: "创建 WS-I 基本配置文件 1.1 可互操作服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6bef68c8ba433e902cfd50e59a3b343e3af08cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>创建 WS-I 基本配置文件 1.1 可互操作服务
将 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务终结点配置为可与 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web 服务客户端互操作：  
  
-   将 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 类型用作服务终结点的绑定类型。  
  
-   不要使用服务终结点上的回调和会话协定功能或事务行为  
  
 您可以根据需要在该绑定上启用对 HTTPS 和传输级客户端身份验证的支持。  
  
 <xref:System.ServiceModel.BasicHttpBinding> 类的以下特性所要求的功能超出了 WS-I 基本配置文件 1.1 的范围：  
  
-   由 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 属性控制的消息传递优化机制 (MTOM) 消息编码。 将此属性保留为其默认值（即 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>）以便不使用 MTOM。  
  
-   由 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 值控制的消息安全提供符合 WS-I 基本安全配置文件 1.0 的 WS-Security 支持。 将此属性保留为其默认值（即 <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>）以便不使用 WS-Security。  
  
 若要使元数据[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]适用于服务[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]，使用 Web 服务客户端生成工具： [Web 服务描述语言工具 (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88)， [Web 服务发现工具 (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)，和`Add Web Reference`功能[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; 必须启用元数据发布。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][发布元数据终结点](../../../docs/framework/wcf/publishing-metadata-endpoints.md)。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示如何添加[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]与兼容的终结点[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]Web 服务客户端在代码和配置文件中。  
  
### <a name="code"></a>代码  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>请参阅  
 [与 ASP.NET Web 服务的互操作性](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
