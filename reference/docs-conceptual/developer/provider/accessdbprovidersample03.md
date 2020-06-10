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
ms.openlocfilehash: 86daab97236ca4be94669f107d5a03abea6f6c91
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633398"
---
# <a name="accessdbprovidersample03"></a><span data-ttu-id="8bb70-102">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="8bb70-102">AccessDBProviderSample03</span></span>

<span data-ttu-id="8bb70-103">このサンプルでは、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)およびコマンドレットの呼び出しをサポートするために、 [Setitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きする方法について説明します。この例では、をオーバーライドしています。 `Get-Item` `Set-Item`</span><span class="sxs-lookup"><span data-stu-id="8bb70-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span> <span data-ttu-id="8bb70-104">このサンプルのプロバイダークラスは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="8bb70-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8bb70-105">対象</span><span class="sxs-lookup"><span data-stu-id="8bb70-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bb70-106">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bb70-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="8bb70-107">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="8bb70-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
> - <span data-ttu-id="8bb70-108">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8bb70-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="8bb70-109">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bb70-109">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="8bb70-110">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="8bb70-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="8bb70-111">「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bb70-111">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="8bb70-112">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bb70-112">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="8bb70-113">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8bb70-113">This sample demonstrates the following:</span></span>

- <span data-ttu-id="8bb70-114">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="8bb70-114">Declaring the `CmdletProvider` attribute.</span></span>
- <span data-ttu-id="8bb70-115">System.servicemodel[プロバイダークラスから派生した](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)プロバイダークラスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="8bb70-115">Defining a provider class that derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
- <span data-ttu-id="8bb70-116">[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを上書きしてコマンドレットの動作を変更し `New-PSDrive` 、ユーザーが新しいドライブを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8bb70-116">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to change the behavior of the `New-PSDrive` cmdlet, allowing the user to create new drives.</span></span>
  <span data-ttu-id="8bb70-117">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `New-PSDrive` )。</span><span class="sxs-lookup"><span data-stu-id="8bb70-117">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>
- <span data-ttu-id="8bb70-118">既存のドライブの削除をサポートするように[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="8bb70-118">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>
- <span data-ttu-id="8bb70-119">このコマンドレットの動作を変更して、ユーザーがデータストアから項目を取得できるようにするには、このメソッドを上書き[します](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)。 `Get-Item`</span><span class="sxs-lookup"><span data-stu-id="8bb70-119">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method to change the behavior of the `Get-Item` cmdlet, allowing the user to retrieve items from the data store.</span></span> <span data-ttu-id="8bb70-120">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Get-Item` )。</span><span class="sxs-lookup"><span data-stu-id="8bb70-120">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>
- <span data-ttu-id="8bb70-121">[Setitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きして、コマンドレットの動作を変更し `Set-Item` 、ユーザーがデータストア内の項目を更新できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="8bb70-121">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method to change the behavior of the `Set-Item` cmdlet, allowing the user to update the items in the data store.</span></span> <span data-ttu-id="8bb70-122">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Get-Item` )。</span><span class="sxs-lookup"><span data-stu-id="8bb70-122">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>
- <span data-ttu-id="8bb70-123">コマンドレットの動作を変更するには、system.servicemodel. [Itemexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドを上書きします。 `Test-Path`</span><span class="sxs-lookup"><span data-stu-id="8bb70-123">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method to change the behavior of the `Test-Path` cmdlet.</span></span> <span data-ttu-id="8bb70-124">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Test-Path` )。</span><span class="sxs-lookup"><span data-stu-id="8bb70-124">(This sample does not show how to add dynamic parameters to the `Test-Path` cmdlet.)</span></span>
- <span data-ttu-id="8bb70-125">指定されたパスが有効かどうかを判断するために、system.string. [Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドを上書きしています。</span><span class="sxs-lookup"><span data-stu-id="8bb70-125">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method to determine if the provided path is valid.</span></span>

## <a name="example"></a><span data-ttu-id="8bb70-126">例</span><span class="sxs-lookup"><span data-stu-id="8bb70-126">Example</span></span>

<span data-ttu-id="8bb70-127">このサンプルでは、Microsoft Access データベースの項目を取得および設定するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8bb70-127">This sample shows how to overwrite the methods needed to get and set items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs" range="11-976":::

## <a name="see-also"></a><span data-ttu-id="8bb70-128">参照</span><span class="sxs-lookup"><span data-stu-id="8bb70-128">See Also</span></span>

[<span data-ttu-id="8bb70-129">システムの................</span><span class="sxs-lookup"><span data-stu-id="8bb70-129">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="8bb70-130">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="8bb70-130">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="8bb70-131">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="8bb70-131">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="8bb70-132">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="8bb70-132">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
