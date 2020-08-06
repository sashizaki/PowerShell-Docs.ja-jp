---
title: AccessDBProviderSample05 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67a10d9192350b339da1b82d9eb367ee4af6ef86
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786851"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="7764d-102">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="7764d-102">AccessDBProviderSample05</span></span>

<span data-ttu-id="7764d-103">このサンプルでは、およびコマンドレットの呼び出しをサポートするためにコンテナーメソッドを上書きする方法を示し `Move-Item` `Join-Path` ます。</span><span class="sxs-lookup"><span data-stu-id="7764d-103">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="7764d-104">これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7764d-104">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="7764d-105">このサンプルのプロバイダークラス[は、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="7764d-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7764d-106">対象</span><span class="sxs-lookup"><span data-stu-id="7764d-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7764d-107">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7764d-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="7764d-108">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="7764d-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="7764d-109">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7764d-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="7764d-110">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7764d-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="7764d-111">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7764d-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="7764d-112">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="7764d-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="7764d-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7764d-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="7764d-114">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7764d-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="7764d-115">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="7764d-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="7764d-116">System.servicemodel クラスから[派生した](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)プロバイダークラスを定義していますが、</span><span class="sxs-lookup"><span data-stu-id="7764d-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="7764d-117">このコマンド[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)レットの動作を変更し `Move-Item` 、ユーザーがある場所から別の場所に項目を移動できるようにするには、このメソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="7764d-117">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="7764d-118">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Move-Item` )。</span><span class="sxs-lookup"><span data-stu-id="7764d-118">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="7764d-119">コマンドレットの動作を変更するには、system.servicemodel[パス \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドを上書きしています。 `Join-Path`</span><span class="sxs-lookup"><span data-stu-id="7764d-119">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="7764d-120">[Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="7764d-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="7764d-121">System.object を上書きしています。 [Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="7764d-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="7764d-122">[Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="7764d-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="7764d-123">[Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドを上書きしています。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="7764d-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="7764d-124">例</span><span class="sxs-lookup"><span data-stu-id="7764d-124">Example</span></span>

<span data-ttu-id="7764d-125">このサンプルでは、Microsoft Access データベースで項目を移動するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7764d-125">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="7764d-126">参照</span><span class="sxs-lookup"><span data-stu-id="7764d-126">See Also</span></span>

[<span data-ttu-id="7764d-127">システムの................</span><span class="sxs-lookup"><span data-stu-id="7764d-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="7764d-128">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="7764d-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="7764d-129">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="7764d-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="7764d-130">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="7764d-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
