---
title: AccessDBProviderSample05 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a26661f2-a63c-4ca7-ad3e-dcb4d32ce5a1
caps.latest.revision: 8
ms.openlocfilehash: 43d18672ec4f52961b2a2460635468a2d6fb41e5
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633381"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="969a0-102">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="969a0-102">AccessDBProviderSample05</span></span>

<span data-ttu-id="969a0-103">このサンプルでは、およびコマンドレットの呼び出しをサポートするためにコンテナーメソッドを上書きする方法を示し `Move-Item` `Join-Path` ます。</span><span class="sxs-lookup"><span data-stu-id="969a0-103">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="969a0-104">これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="969a0-104">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="969a0-105">このサンプルのプロバイダークラス[は、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="969a0-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="969a0-106">対象</span><span class="sxs-lookup"><span data-stu-id="969a0-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="969a0-107">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="969a0-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="969a0-108">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="969a0-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="969a0-109">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="969a0-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="969a0-110">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="969a0-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="969a0-111">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="969a0-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="969a0-112">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="969a0-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="969a0-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="969a0-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="969a0-114">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="969a0-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="969a0-115">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="969a0-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="969a0-116">System.servicemodel クラスから[派生した](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)プロバイダークラスを定義していますが、</span><span class="sxs-lookup"><span data-stu-id="969a0-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="969a0-117">このコマンド[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)レットの動作を変更し `Move-Item` 、ユーザーがある場所から別の場所に項目を移動できるようにするには、このメソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="969a0-117">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="969a0-118">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Move-Item` )。</span><span class="sxs-lookup"><span data-stu-id="969a0-118">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="969a0-119">コマンドレットの動作を変更するには、system.servicemodel[パス \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドを上書きしています。 `Join-Path`</span><span class="sxs-lookup"><span data-stu-id="969a0-119">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="969a0-120">[Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="969a0-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="969a0-121">System.object を上書きしています。 [Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="969a0-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="969a0-122">[Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="969a0-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="969a0-123">[Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="969a0-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="969a0-124">例</span><span class="sxs-lookup"><span data-stu-id="969a0-124">Example</span></span>

<span data-ttu-id="969a0-125">このサンプルでは、Microsoft Access データベースで項目を移動するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="969a0-125">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="969a0-126">参照</span><span class="sxs-lookup"><span data-stu-id="969a0-126">See Also</span></span>

[<span data-ttu-id="969a0-127">システムの................</span><span class="sxs-lookup"><span data-stu-id="969a0-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="969a0-128">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="969a0-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="969a0-129">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="969a0-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="969a0-130">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="969a0-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
