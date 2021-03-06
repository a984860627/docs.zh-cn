---
title: "如何：查找由 ControlTemplate 生成的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e06de393fa9020277d01f24a332cddb9683bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-controltemplate-generated-elements"></a>如何：查找由 ControlTemplate 生成的元素
此示例演示如何查找元素所生成的<xref:System.Windows.Controls.ControlTemplate>。  
  
## <a name="example"></a>示例  
 下面的示例演示创建一个简单样式<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>类：  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 若要在应用该模板后，请查找模板内的元素，可以调用<xref:System.Windows.FrameworkTemplate.FindName%2A>方法<xref:System.Windows.Controls.Control.Template%2A>。 下面的示例创建一个消息框，显示的实际宽度值<xref:System.Windows.Controls.Grid>控件模板中：  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>请参阅  
 [查找由 DataTemplate 生成的元素](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [WPF XAML 名称范围](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
