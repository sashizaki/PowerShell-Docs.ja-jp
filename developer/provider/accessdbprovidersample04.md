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
ms.openlocfilehash: fd013384a4b588bcdb397d7771425fe5c031c48f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856698"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="518e8-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="518e8-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="518e8-103">このサンプルの呼び出しをサポートするためにコンテナー メソッドを上書きする方法を示しています、 `Copy-Item`、 `Get-ChildItem`、 `New-Item`、および`Remove-Item`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="518e8-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="518e8-104">これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="518e8-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="518e8-105">コンテナーは、共通の親項目の子項目のグループです。</span><span class="sxs-lookup"><span data-stu-id="518e8-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="518e8-106">このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="518e8-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="518e8-107">使用例</span><span class="sxs-lookup"><span data-stu-id="518e8-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="518e8-108">ほとんどの場合、プロバイダー クラスの継承元、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="518e8-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="518e8-109">このサンプルでは、次の項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="518e8-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="518e8-110">宣言、`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="518e8-110">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="518e8-111">派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="518e8-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

- <span data-ttu-id="518e8-112">上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Copyitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドの動作を変更する、`Copy-Item`コマンドレットに渡してアイテムを別の 1 つの場所にコピーするユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="518e8-112">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Copyitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="518e8-113">(このサンプルで動的パラメーターを追加する方法が表示されない、`Copy-Item`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="518e8-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>

- <span data-ttu-id="518e8-114">上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)ユーザーが、親アイテムの子項目を取得する Get ChildItems コマンドレットの動作を変更する方法.</span><span class="sxs-lookup"><span data-stu-id="518e8-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="518e8-115">(このサンプルは、Get ChildItems コマンドレットに動的パラメーターを追加する方法を表示はされません)。</span><span class="sxs-lookup"><span data-stu-id="518e8-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>

- <span data-ttu-id="518e8-116">上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッド Get ChildItems コマンドレットの動作を変更するときに、`Name`コマンドレットのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="518e8-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>

- <span data-ttu-id="518e8-117">上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドの動作を変更する、`New-Item`コマンドレットは、ユーザーがデータ ストアに項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="518e8-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="518e8-118">(このサンプルで動的パラメーターを追加する方法が表示されない、`New-Item`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="518e8-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>

- <span data-ttu-id="518e8-119">上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドの動作を変更する、`Remove-Item`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="518e8-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="518e8-120">(このサンプルで動的パラメーターを追加する方法が表示されない、`Remove-Item`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="518e8-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="518e8-121">例</span><span class="sxs-lookup"><span data-stu-id="518e8-121">Example</span></span>

<span data-ttu-id="518e8-122">このサンプルでは、コピー、作成、および子の親項目の項目を取得するためのメソッドと同様に、項目を削除するためのメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="518e8-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="518e8-123">参照</span><span class="sxs-lookup"><span data-stu-id="518e8-123">See Also</span></span>

[<span data-ttu-id="518e8-124">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="518e8-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="518e8-125">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="518e8-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="518e8-126">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="518e8-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="518e8-127">Windows PowerShell プロバイダーのデザイン</span><span class="sxs-lookup"><span data-stu-id="518e8-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)