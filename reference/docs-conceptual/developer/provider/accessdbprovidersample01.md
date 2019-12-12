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
# <a name="accessdbprovidersample01"></a><span data-ttu-id="b6596-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="b6596-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="b6596-103">このサンプルでは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスから直接派生するプロバイダークラスを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b6596-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="b6596-104">すべてを網羅しておく目的でここに含めておきます。</span><span class="sxs-lookup"><span data-stu-id="b6596-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b6596-105">使用例</span><span class="sxs-lookup"><span data-stu-id="b6596-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6596-106">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6596-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="b6596-107">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="b6596-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="b6596-108">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6596-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="b6596-109">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b6596-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="b6596-110">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6596-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="b6596-111">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="b6596-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="b6596-112">「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6596-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="b6596-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6596-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="b6596-114">このサンプルは、次の操作方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b6596-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="b6596-115">`CmdletProvider` 属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="b6596-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="b6596-116">[システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)の.......................................</span><span class="sxs-lookup"><span data-stu-id="b6596-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="b6596-117">例</span><span class="sxs-lookup"><span data-stu-id="b6596-117">Example</span></span>

<span data-ttu-id="b6596-118">このサンプルでは、プロバイダークラスを定義する方法と、`CmdletProvider` 属性を宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b6596-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b6596-119">参照</span><span class="sxs-lookup"><span data-stu-id="b6596-119">See Also</span></span>

[<span data-ttu-id="b6596-120">システムの................</span><span class="sxs-lookup"><span data-stu-id="b6596-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="b6596-121">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="b6596-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="b6596-122">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="b6596-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="b6596-123">Windows PowerShell プロバイダーの設計</span><span class="sxs-lookup"><span data-stu-id="b6596-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)