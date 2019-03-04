---
title: AccessDBProviderSample01 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 853b7e5d-76c1-490e-8269-0ef31ba2ff13
caps.latest.revision: 10
ms.openlocfilehash: dc1ae92af8a57d6197b595db8e098256ac444b78
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854158"
---
# <a name="accessdbprovidersample01"></a>AccessDBProviderSample01

このサンプルから直接派生するプロバイダー クラスを宣言する方法を示しています、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラス。 すべてを網羅しておく目的でここに含めておきます。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。
>
> -   [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。 参照してください[AccessDBProviderSample03](./accessdbprovidersample03.md)します。
> -   [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。 参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。
> -   [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。 参照してください[AccessDBProviderSample05](./accessdbprovidersample05.md)します。
>
> プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。

このサンプルでは、次の項目を示しています。

- 宣言、`CmdletProvider`属性。

- 直接派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラス。

## <a name="example"></a>例

このサンプルでは、プロバイダー クラスを定義する方法と宣言する方法を示しています。、`CmdletProvider`属性。

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  /// <summary>
  /// This sample shows how to declare a provider class and how to
  /// declare the CmdletProvider attribute.
  /// </summary>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : CmdletProvider
  {
    // Add provider logic here.
  }
}
```

## <a name="see-also"></a>参照

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーのデザイン](./provider-types.md)