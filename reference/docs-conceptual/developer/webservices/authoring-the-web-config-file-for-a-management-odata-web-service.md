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
ms.openlocfilehash: 8e5897c3df38689e80d2135dfb82898bf9a05b86
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561483"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a>Management OData Web サービスの Web.config ファイルを作成する

Management OData web サービスを配置する前に、XML スキーマファイルと、 [Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization)および[register-pssessionconfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration)インターフェイスを実装する dll をポイントするように web.config ファイルを構成する必要があります。このような場合には、

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

[Management OData Web サービスのカスタム認可を実装する](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[Management OData Web サービスの SessionConfiguration を実装する](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[Management OData Web サービスの MOF スキーマ ファイルを作成する](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[Management OData Web サービスの XML スキーマ ファイルを作成する](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[Management OData Web サービスを作成する](./creating-a-management-odata-web-service.md)
