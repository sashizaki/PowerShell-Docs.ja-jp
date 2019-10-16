---
title: AccessDBProviderSample04 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: 7096f8066568c214a5902f6943a2c093932d3b56
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366341"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="3e771-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="3e771-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="3e771-103">このサンプルでは、コンテナーメソッドを上書きして、`Copy-Item`、`Get-ChildItem`、`New-Item`、および `Remove-Item` コマンドレットの呼び出しをサポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e771-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="3e771-104">これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e771-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="3e771-105">コンテナーは、共通の親項目の子項目のグループです。</span><span class="sxs-lookup"><span data-stu-id="3e771-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="3e771-106">このサンプルのプロバイダークラスは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="3e771-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3e771-107">サンプル</span><span class="sxs-lookup"><span data-stu-id="3e771-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e771-108">プロバイダークラスは、ほとんどの場合、[システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)から派生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3e771-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="3e771-109">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="3e771-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="3e771-110">@No__t-0 属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="3e771-110">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="3e771-111">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生したプロバイダークラスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="3e771-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

- <span data-ttu-id="3e771-112">[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドを上書きして、ユーザーが1つの場所から別の場所に項目をコピーできるようにする `Copy-Item` コマンドレットの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="3e771-112">Overwriting the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="3e771-113">(このサンプルでは、`Copy-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="3e771-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>

- <span data-ttu-id="3e771-114">[Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドを上書きして、ChildItems コマンドレットの動作を変更します。これにより、ユーザーは親項目の子項目を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e771-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="3e771-115">(このサンプルでは、ChildItems コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="3e771-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>

- <span data-ttu-id="3e771-116">コマンドレットの `Name` パラメーターが指定されている場合に、ChildItems コマンドレットの動作を変更するには、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="3e771-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>

- <span data-ttu-id="3e771-117">Containercmdletprovider コマンドレット @no__t の動作を変更するには、 [Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドを上書きします。これにより、ユーザーがデータストアに項目を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e771-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="3e771-118">(このサンプルでは、`New-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="3e771-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>

- <span data-ttu-id="3e771-119">[Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドを上書きして、`Remove-Item` コマンドレットの動作を変更しています。</span><span class="sxs-lookup"><span data-stu-id="3e771-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="3e771-120">(このサンプルでは、`Remove-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="3e771-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="3e771-121">例</span><span class="sxs-lookup"><span data-stu-id="3e771-121">Example</span></span>

<span data-ttu-id="3e771-122">このサンプルでは、項目をコピー、作成、および削除するために必要なメソッドと、親項目の子項目を取得するメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e771-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="3e771-123">参照</span><span class="sxs-lookup"><span data-stu-id="3e771-123">See Also</span></span>

[<span data-ttu-id="3e771-124">システムの................</span><span class="sxs-lookup"><span data-stu-id="3e771-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="3e771-125">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="3e771-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="3e771-126">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="3e771-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="3e771-127">Windows PowerShell プロバイダーの設計</span><span class="sxs-lookup"><span data-stu-id="3e771-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
