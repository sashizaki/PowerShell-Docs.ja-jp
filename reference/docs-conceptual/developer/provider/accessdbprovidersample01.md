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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360001"
---
# <a name="accessdbprovidersample01"></a>AccessDBProviderSample01

このサンプルでは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスから直接派生するプロバイダークラスを宣言する方法を示します。 すべてを網羅しておく目的でここに含めておきます。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。
>
> -   ...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。 「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。
> -   [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。 「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。
> -   ...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。
>
> プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。

このサンプルは、次の操作方法を示します。

- `CmdletProvider` 属性を宣言しています。

- [システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)の.......................................

## <a name="example"></a>例

このサンプルでは、プロバイダークラスを定義する方法と、`CmdletProvider` 属性を宣言する方法を示します。

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

[システムの................](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[Containercmdletprovider (システム管理)](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[システムの管理...。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーの設計](./provider-types.md)