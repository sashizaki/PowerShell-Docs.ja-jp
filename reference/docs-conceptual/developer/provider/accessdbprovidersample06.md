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
ms.openlocfilehash: 9c00ec6de987729fec42dc57245a949d11e31f4b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366331"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="edce1-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="edce1-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="edce1-103">このサンプルでは、`Clear-Content`、`Get-Content`、および `Set-Content` コマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="edce1-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="edce1-104">これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edce1-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="edce1-105">このサンプルのプロバイダークラスは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを実装しています。この[クラスは、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生していますが、</span><span class="sxs-lookup"><span data-stu-id="edce1-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="edce1-106">使用例</span><span class="sxs-lookup"><span data-stu-id="edce1-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edce1-107">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="edce1-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="edce1-108">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="edce1-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="edce1-109">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edce1-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="edce1-110">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="edce1-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="edce1-111">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edce1-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="edce1-112">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="edce1-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="edce1-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edce1-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="edce1-114">このサンプルは、次の操作方法を示します。</span><span class="sxs-lookup"><span data-stu-id="edce1-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="edce1-115">`CmdletProvider` 属性を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="edce1-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="edce1-116">[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを宣言する、system.servicemodel クラスから派生したプロバイダークラスを定義します。[このクラスは](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)、このクラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="edce1-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

- <span data-ttu-id="edce1-117">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを上書きして、`Clear-Content` コマンドレットの動作を変更し、ユーザーが項目からコンテンツを削除できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="edce1-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="edce1-118">(このサンプルでは、`Clear-Content` コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="edce1-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>

- <span data-ttu-id="edce1-119">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを上書きして、`Get-Content` コマンドレットの動作を変更し、ユーザーが項目の内容を取得できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="edce1-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="edce1-120">(このサンプルでは、`Get-Content` コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="edce1-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>

- <span data-ttu-id="edce1-121">`Set-Content` コマンドレットの動作を変更して、ユーザーが項目の内容を更新できるようにするには、[このメソッドを上書きします](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter)。</span><span class="sxs-lookup"><span data-stu-id="edce1-121">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="edce1-122">(このサンプルでは、`Set-Content` コマンドレットに動的パラメーターを追加する方法については説明しません)。</span><span class="sxs-lookup"><span data-stu-id="edce1-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="edce1-123">例</span><span class="sxs-lookup"><span data-stu-id="edce1-123">Example</span></span>

<span data-ttu-id="edce1-124">このサンプルでは、Microsoft Access データベースの項目の内容をクリア、取得、および設定するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="edce1-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="edce1-125">参照</span><span class="sxs-lookup"><span data-stu-id="edce1-125">See Also</span></span>

[<span data-ttu-id="edce1-126">システムの................</span><span class="sxs-lookup"><span data-stu-id="edce1-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="edce1-127">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="edce1-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="edce1-128">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="edce1-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="edce1-129">Windows PowerShell プロバイダーの設計</span><span class="sxs-lookup"><span data-stu-id="edce1-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
