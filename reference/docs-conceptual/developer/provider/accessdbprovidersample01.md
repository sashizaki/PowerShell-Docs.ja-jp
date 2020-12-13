---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample01
description: AccessDBProviderSample01
ms.openlocfilehash: 8bdfa3ad492935a22ce06846294c02961cab2c65
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653759"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="48617-103">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="48617-103">AccessDBProviderSample01</span></span>

<span data-ttu-id="48617-104">このサンプルでは、system.servicemodel [プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) クラスから直接派生するプロバイダークラスを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="48617-104">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="48617-105">すべてを網羅しておく目的でここに含めておきます。</span><span class="sxs-lookup"><span data-stu-id="48617-105">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="48617-106">対象</span><span class="sxs-lookup"><span data-stu-id="48617-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48617-107">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48617-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="48617-108">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="48617-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="48617-109">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48617-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="48617-110">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="48617-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="48617-111">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48617-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="48617-112">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="48617-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="48617-113">「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48617-113">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="48617-114">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48617-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="48617-115">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="48617-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="48617-116">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="48617-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="48617-117">[システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)の.......................................</span><span class="sxs-lookup"><span data-stu-id="48617-117">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="48617-118">例</span><span class="sxs-lookup"><span data-stu-id="48617-118">Example</span></span>

<span data-ttu-id="48617-119">このサンプルでは、プロバイダークラスを定義する方法と、属性を宣言する方法を示し `CmdletProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="48617-119">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="48617-120">参照</span><span class="sxs-lookup"><span data-stu-id="48617-120">See Also</span></span>

[<span data-ttu-id="48617-121">システムの................</span><span class="sxs-lookup"><span data-stu-id="48617-121">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="48617-122">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="48617-122">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="48617-123">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="48617-123">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="48617-124">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="48617-124">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
