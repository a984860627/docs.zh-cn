---
title: "WCF 和 WebSocket"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e84bf7a94a6a6fa980e223daf0a6c7aaf489bb6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-and-websockets"></a>WCF 和 WebSocket
.NET Framework 4.5 引入了对 Windows Communication Foundation 中的 WebSocket 的支持。  WebSocket 是一种高效的、基于标准的技术，可通过标准 HTTP 端口 80 和 443 实现双向通信。 使用标准 HTTP 端口，WebSocket 可通过中介跨 Web 进行通信。  添加了两个新的标准绑定以支持通过 WebSocket 传输进行的通信。 <xref:System.ServiceModel.NetHttpBinding> 和 <xref:System.ServiceModel.NetHttpsBinding>。 可以在上配置 Websocket 特定设置<xref:System.ServiceModel.Channels.HttpTransportBindingElement>通过访问<xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A>属性。
  
## <a name="in-this-section"></a>本节内容  
 [使用 NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 讨论 <xref:System.ServiceModel.NetHttpBinding> 以及如何对其进行配置。  
  
 [如何：创建通过 Web 套接字进行通信的 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 说明如何创建通过 Websocket 进行通信的 WCF 服务。  
  
## <a name="reference"></a>参考  
  
## <a name="related-sections"></a>相关章节
