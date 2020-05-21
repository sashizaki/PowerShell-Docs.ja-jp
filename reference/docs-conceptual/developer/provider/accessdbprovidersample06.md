---
title: AccessDBProviderSample06 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46dc0657-110f-4367-8bb6-a95dca2c5016
caps.latest.revision: 8
ms.openlocfilehash: 52c1fac134f7184462842a56f466f634aec1222c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692435"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="7b3ee-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="7b3ee-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="7b3ee-103">このサンプル `Clear-Content` では、、 `Get-Content` 、およびコマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示し `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="7b3ee-104">これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="7b3ee-105">このサンプルのプロバイダークラスは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを実装しています。この[クラスは、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生していますが、</span><span class="sxs-lookup"><span data-stu-id="7b3ee-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7b3ee-106">対象</span><span class="sxs-lookup"><span data-stu-id="7b3ee-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b3ee-107">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="7b3ee-108">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="7b3ee-109">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="7b3ee-110">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="7b3ee-111">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="7b3ee-112">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="7b3ee-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="7b3ee-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="7b3ee-114">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="7b3ee-115">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-115">Declaring the `CmdletProvider` attribute.</span></span>
- <span data-ttu-id="7b3ee-116">[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを宣言する、system.servicemodel クラスから派生したプロバイダークラスを定義します。[このクラスは](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)、このクラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>
- <span data-ttu-id="7b3ee-117">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを上書きして、コマンドレットの動作を変更し `Clear-Content` 、ユーザーが項目からコンテンツを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="7b3ee-118">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Clear-Content` )。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>
- <span data-ttu-id="7b3ee-119">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを上書きして、コマンドレットの動作を変更し `Get-Content` 、ユーザーが項目の内容を取得できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="7b3ee-120">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Get-Content` )。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>
- <span data-ttu-id="7b3ee-121">コマンドレットの動作を変更して、ユーザーが項目の内容を更新できるようにするには、このメソッドを上書き[します。](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) `Set-Content`</span><span class="sxs-lookup"><span data-stu-id="7b3ee-121">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="7b3ee-122">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Set-Content` )。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="7b3ee-123">例</span><span class="sxs-lookup"><span data-stu-id="7b3ee-123">Example</span></span>

<span data-ttu-id="7b3ee-124">このサンプルでは、Microsoft Access データベースの項目の内容をクリア、取得、および設定するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="7b3ee-125">参照</span><span class="sxs-lookup"><span data-stu-id="7b3ee-125">See Also</span></span>

[<span data-ttu-id="7b3ee-126">システムの................</span><span class="sxs-lookup"><span data-stu-id="7b3ee-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="7b3ee-127">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="7b3ee-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="7b3ee-128">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="7b3ee-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="7b3ee-129">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="7b3ee-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
