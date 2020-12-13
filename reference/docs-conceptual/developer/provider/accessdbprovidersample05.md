---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample05
description: AccessDBProviderSample05
ms.openlocfilehash: ad273720ded0b200530f4f81482d01a8fbb82aa3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92656920"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="c6893-103">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="c6893-103">AccessDBProviderSample05</span></span>

<span data-ttu-id="c6893-104">このサンプルでは、およびコマンドレットの呼び出しをサポートするためにコンテナーメソッドを上書きする方法を示し `Move-Item` `Join-Path` ます。</span><span class="sxs-lookup"><span data-stu-id="c6893-104">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="c6893-105">これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6893-105">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="c6893-106">このサンプルのプロバイダークラス [は、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="c6893-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c6893-107">対象</span><span class="sxs-lookup"><span data-stu-id="c6893-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6893-108">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6893-108">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="c6893-109">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="c6893-109">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="c6893-110">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6893-110">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="c6893-111">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6893-111">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="c6893-112">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6893-112">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="c6893-113">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="c6893-113">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="c6893-114">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6893-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="c6893-115">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6893-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="c6893-116">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="c6893-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="c6893-117">System.servicemodel クラスから [派生した](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) プロバイダークラスを定義していますが、</span><span class="sxs-lookup"><span data-stu-id="c6893-117">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="c6893-118">このコマンド[](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)レットの動作を変更し `Move-Item` 、ユーザーがある場所から別の場所に項目を移動できるようにするには、このメソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c6893-118">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="c6893-119">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Move-Item` )。</span><span class="sxs-lookup"><span data-stu-id="c6893-119">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="c6893-120">コマンドレットの動作を変更するには、system.servicemodel[パス \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドを上書きしています。 `Join-Path`</span><span class="sxs-lookup"><span data-stu-id="c6893-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="c6893-121">[Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="c6893-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="c6893-122">System.object を上書きしています。 [Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c6893-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="c6893-123">[Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="c6893-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="c6893-124">[Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="c6893-124">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="c6893-125">例</span><span class="sxs-lookup"><span data-stu-id="c6893-125">Example</span></span>

<span data-ttu-id="c6893-126">このサンプルでは、Microsoft Access データベースで項目を移動するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6893-126">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="c6893-127">参照</span><span class="sxs-lookup"><span data-stu-id="c6893-127">See Also</span></span>

[<span data-ttu-id="c6893-128">システムの................</span><span class="sxs-lookup"><span data-stu-id="c6893-128">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="c6893-129">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="c6893-129">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="c6893-130">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="c6893-130">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="c6893-131">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="c6893-131">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
