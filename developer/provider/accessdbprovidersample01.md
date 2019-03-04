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
# <a name="accessdbprovidersample01"></a><span data-ttu-id="9d11a-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="9d11a-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="9d11a-103">このサンプルから直接派生するプロバイダー クラスを宣言する方法を示しています、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="9d11a-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="9d11a-104">すべてを網羅しておく目的でここに含めておきます。</span><span class="sxs-lookup"><span data-stu-id="9d11a-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="9d11a-105">使用例</span><span class="sxs-lookup"><span data-stu-id="9d11a-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d11a-106">プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。</span><span class="sxs-lookup"><span data-stu-id="9d11a-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="9d11a-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="9d11a-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="9d11a-108">参照してください[AccessDBProviderSample03](./accessdbprovidersample03.md)します。</span><span class="sxs-lookup"><span data-stu-id="9d11a-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="9d11a-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="9d11a-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="9d11a-110">参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。</span><span class="sxs-lookup"><span data-stu-id="9d11a-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="9d11a-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="9d11a-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="9d11a-112">参照してください[AccessDBProviderSample05](./accessdbprovidersample05.md)します。</span><span class="sxs-lookup"><span data-stu-id="9d11a-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="9d11a-113">プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="9d11a-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="9d11a-114">このサンプルでは、次の項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="9d11a-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="9d11a-115">宣言、`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="9d11a-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="9d11a-116">直接派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="9d11a-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="9d11a-117">例</span><span class="sxs-lookup"><span data-stu-id="9d11a-117">Example</span></span>

<span data-ttu-id="9d11a-118">このサンプルでは、プロバイダー クラスを定義する方法と宣言する方法を示しています。、`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="9d11a-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9d11a-119">参照</span><span class="sxs-lookup"><span data-stu-id="9d11a-119">See Also</span></span>

[<span data-ttu-id="9d11a-120">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="9d11a-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="9d11a-121">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="9d11a-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="9d11a-122">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="9d11a-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="9d11a-123">Windows PowerShell プロバイダーのデザイン</span><span class="sxs-lookup"><span data-stu-id="9d11a-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)