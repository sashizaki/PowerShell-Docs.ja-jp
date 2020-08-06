---
title: AccessDBProviderSample01 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 50ec218e8d0fe6b2be5c8ac00956f72c6723f84a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786919"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="b4350-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="b4350-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="b4350-103">このサンプルでは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスから直接派生するプロバイダークラスを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b4350-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="b4350-104">すべてを網羅しておく目的でここに含めておきます。</span><span class="sxs-lookup"><span data-stu-id="b4350-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b4350-105">対象</span><span class="sxs-lookup"><span data-stu-id="b4350-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4350-106">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4350-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="b4350-107">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="b4350-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="b4350-108">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4350-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="b4350-109">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b4350-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="b4350-110">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4350-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="b4350-111">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="b4350-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="b4350-112">「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4350-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="b4350-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4350-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="b4350-114">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b4350-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="b4350-115">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="b4350-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="b4350-116">[システム](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)の.......................................</span><span class="sxs-lookup"><span data-stu-id="b4350-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="b4350-117">例</span><span class="sxs-lookup"><span data-stu-id="b4350-117">Example</span></span>

<span data-ttu-id="b4350-118">このサンプルでは、プロバイダークラスを定義する方法と、属性を宣言する方法を示し `CmdletProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="b4350-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="b4350-119">参照</span><span class="sxs-lookup"><span data-stu-id="b4350-119">See Also</span></span>

[<span data-ttu-id="b4350-120">システムの................</span><span class="sxs-lookup"><span data-stu-id="b4350-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="b4350-121">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="b4350-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="b4350-122">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="b4350-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="b4350-123">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="b4350-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
