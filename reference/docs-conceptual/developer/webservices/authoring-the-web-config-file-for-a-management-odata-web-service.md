---
title: 管理 OData web サービスの Web.config ファイルを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569f5d5-9746-40c0-be5e-f218bc4560f7
caps.latest.revision: 4
ms.openlocfilehash: f52953ee091f05df5f355719ecba788d3d5ee055
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359791"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a>Management OData Web サービスの Web.config ファイルを作成する

Management OData web サービスをデプロイする前に、XML スキーマファイルと、 [Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization)を[実装する dll を参照するように web.config ファイルを構成する必要があります。Register-pssessionconfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration)インターフェイス () を行います。

## <a name="sample-config-file"></a>サンプル構成ファイル

次に、web サービスの web.config ファイルの例を示します。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
   <configSections>
      <section name="managementOdata" type="Microsoft.Management.Odata.Core.DSConfiguration, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL" />
   </configSections>
   <managementOdata schemaFileName="Schema.mof" resourceMappingFileName="Schema.xml">
      <customAuthorization type="Microsoft.Samples.Management.OData.RoleBasedPlugins.CustomAuthorization" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      <powershell>
         <sessionConfiguration type="Microsoft.Samples.Management.OData.RoleBasedPlugins.SessionConfiguration" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      </powershell>
      <commandInvocation enabled="true" />
      <wcfDataServicesConfig>
      </wcfDataServicesConfig>
   </managementOdata>
   <system.serviceModel>
      <behaviors>
         <serviceBehaviors>
            <behavior>
                  <serviceAuthorization serviceAuthorizationManagerType="Microsoft.Management.Odata.Core.CustomAuthorizationManager, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
            </behavior>
         </serviceBehaviors>
      </behaviors>
      <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
   </system.serviceModel>
   <system.webServer>
      <security>
         <authentication>
            <anonymousAuthentication enabled="false" />
            <basicAuthentication enabled="true" />
            <windowsAuthentication enabled="false" />
         </authentication>
      </security>
  </system.webServer>
</configuration>

```

## <a name="see-also"></a>参照

[管理 OData web サービスのカスタム承認の実装](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[管理 OData web サービスに SessionConfiguration を実装する](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[管理用の OData web サービスの MOF スキーマファイルを作成する](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[管理用の OData web サービス用の XML スキーマファイルの作成](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[管理 OData Web サービスの作成](./creating-a-management-odata-web-service.md)