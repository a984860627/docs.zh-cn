---
title: '&lt;audienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 69c96698b309a789b4527c76e1fe8b8b99811a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
指定是可接受的信赖方 (RP) 标识符的 Uri 的集。 除非允许的受众 Uri 之一划分作用域，将不会接受令牌。  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<audienceUris >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|mode|<xref:System.IdentityModel.Selectors.AudienceUriMode>值，该值指定是否应该对传入令牌应用受众限制。 可能的值为"始终"，"从不"，并"BearerKeyOnly"。 默认值为"始终"。 可选。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|`<add value=xs:string>`|将添加指定的 URI`value`到 audienceUris 集合属性。 需要 `value` 属性。 URI 是区分大小写。|  
|`<clear>`|清除 audienceUris 集合。 所有标识符都从集合中都移除。|  
|`<remove value=xs:string>`|删除指定的 URI`value`从 audienceUris 集合的属性。 需要 `value` 属性。 URI 是区分大小写。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|提供配置集合的安全令牌处理程序。|  
  
## <a name="remarks"></a>备注  
 默认情况下，该集合为空;使用`<add>`， `<clear>`，和`<remove>`元素来修改该集合。 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>和<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>对象，请使用来配置所有的受众 URI 集合中的值允许受众 URI 限制在<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象。  
  
 `<audienceUris>`元素表示由<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>类。 添加到集合的单个 URI 由<xref:System.IdentityModel.Configuration.AudienceUriElement>类。  
  
> [!NOTE]
>  使用`<audienceUris>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。 上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何配置应用程序的可接受受众 Uri。 此示例将配置单个 URI。 将接受针对此 URI 范围内的令牌，将拒绝所有其他用户。  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
