---
title: "简单策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 884a099c1334b53c904173987d2f1ccfe6dd741a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="simple-policy"></a>简单策略
此示例演示如何在工作流中使用 <xref:System.Workflow.Activities.PolicyActivity> 活动。  
  
 此示例中的顺序工作流是通过使用 <xref:System.Workflow.Activities.PolicyActivity> 活动创建的。 工作流定义 `orderValue`, `customerType`，以及用于定义产品折扣工作流的 `discount` 字段。 规则文件中定义的规则设置基于 `orderValue` 和 `customerType` 的折扣值。 `orderValue` 和 `customerType` 在 `SimplePolicyWorkflow` 类定义中设置，并且可加以更改以改变行为。 生成的折扣将写入 <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> 事件处理程序中的控制台，该事件处理程序是在 `SimplePolicyWorkflow` 类中定义的。  
  
### <a name="to-build-the-sample"></a>生成示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  按 Ctrl+F5 运行解决方案而不进行调试。  
  
### <a name="to-run-the-sample"></a>运行示例  
  
-   在 SDK 命令提示窗口中，运行 SimplePolicy\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 SimplePolicy\bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [高级策略](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
