---
title: AccessDBProviderSample03 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e576199-49c7-4355-9686-f9ed40c64a5f
caps.latest.revision: 10
ms.openlocfilehash: 57b6cfaa5f29300c60a5a745797111b6beba3133
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081072"
---
# <a name="accessdbprovidersample03"></a><span data-ttu-id="e0caf-102">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="e0caf-102">AccessDBProviderSample03</span></span>

<span data-ttu-id="e0caf-103">このサンプルを上書きする方法を示しています、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッド呼び出しをサポートする、`Get-Item`と`Set-Item`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="e0caf-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span> <span data-ttu-id="e0caf-104">このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="e0caf-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e0caf-105">使用例</span><span class="sxs-lookup"><span data-stu-id="e0caf-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0caf-106">プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。</span><span class="sxs-lookup"><span data-stu-id="e0caf-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="e0caf-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="e0caf-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
> -   <span data-ttu-id="e0caf-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="e0caf-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="e0caf-109">参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0caf-109">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="e0caf-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="e0caf-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="e0caf-111">参照してください[AccessDBProviderSample05](./accessdbprovidersample05.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0caf-111">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="e0caf-112">プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0caf-112">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="e0caf-113">このサンプルでは、次の項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0caf-113">This sample demonstrates the following:</span></span>

- <span data-ttu-id="e0caf-114">宣言、`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="e0caf-114">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="e0caf-115">派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="e0caf-115">Defining a provider class that derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

- <span data-ttu-id="e0caf-116">上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドの動作を変更する、`New-PSDrive`コマンドレットは、ユーザーが新しいドライブを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0caf-116">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to change the behavior of the `New-PSDrive` cmdlet, allowing the user to create new drives.</span></span> <span data-ttu-id="e0caf-117">(このサンプルで動的パラメーターを追加する方法が表示されない、`New-PSDrive`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="e0caf-117">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="e0caf-118">上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを既存のドライブの削除をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e0caf-118">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

- <span data-ttu-id="e0caf-119">上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッドの動作を変更する、`Get-Item`コマンドレットは、ユーザーがデータ ストアから項目を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0caf-119">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method to change the behavior of the `Get-Item` cmdlet, allowing the user to retrieve items from the data store.</span></span> <span data-ttu-id="e0caf-120">(このサンプルで動的パラメーターを追加する方法が表示されない、`Get-Item`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="e0caf-120">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="e0caf-121">上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドの動作を変更する、`Set-Item`コマンドレットは、ユーザーがデータ ストア内の項目を更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0caf-121">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method to change the behavior of the `Set-Item` cmdlet, allowing the user to update the items in the data store.</span></span> <span data-ttu-id="e0caf-122">(このサンプルで動的パラメーターを追加する方法が表示されない、`Get-Item`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="e0caf-122">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="e0caf-123">上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドの動作を変更する、`Test-Path`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="e0caf-123">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method to change the behavior of the `Test-Path` cmdlet.</span></span> <span data-ttu-id="e0caf-124">(このサンプルで動的パラメーターを追加する方法が表示されない、`Test-Path`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="e0caf-124">(This sample does not show how to add dynamic parameters to the `Test-Path` cmdlet.)</span></span>

- <span data-ttu-id="e0caf-125">上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドを指定されたパスが有効であるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e0caf-125">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method to determine if the provided path is valid.</span></span>

## <a name="example"></a><span data-ttu-id="e0caf-126">例</span><span class="sxs-lookup"><span data-stu-id="e0caf-126">Example</span></span>

<span data-ttu-id="e0caf-127">このサンプルでは、取得および Microsoft Access データの基本項目を設定するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e0caf-127">This sample shows how to overwrite the methods needed to get and set items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="e0caf-128">参照</span><span class="sxs-lookup"><span data-stu-id="e0caf-128">See Also</span></span>

[<span data-ttu-id="e0caf-129">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="e0caf-129">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="e0caf-130">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="e0caf-130">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="e0caf-131">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="e0caf-131">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="e0caf-132">Windows PowerShell プロバイダーのデザイン</span><span class="sxs-lookup"><span data-stu-id="e0caf-132">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)