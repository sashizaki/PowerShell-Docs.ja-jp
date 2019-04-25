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
ms.openlocfilehash: f020f023f9a379ff8a610edb7d5dcfe207170394
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080987"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="0dcfa-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="0dcfa-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="0dcfa-103">このサンプルは、呼び出しをサポートするコンテンツのメソッドを上書きする方法を示します、 `Clear-Content`、 `Get-Content`、および`Set-Content`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="0dcfa-104">これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="0dcfa-105">このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス、およびその実装、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="0dcfa-106">使用例</span><span class="sxs-lookup"><span data-stu-id="0dcfa-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dcfa-107">プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="0dcfa-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="0dcfa-109">参照してください[AccessDBProviderSample03](./accessdbprovidersample03.md)します。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="0dcfa-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="0dcfa-111">参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="0dcfa-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="0dcfa-113">プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="0dcfa-114">このサンプルでは、次の項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="0dcfa-115">宣言、`CmdletProvider`属性。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="0dcfa-116">派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)とクラスを宣言、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

- <span data-ttu-id="0dcfa-117">上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドの動作を変更する、`Clear-Content`コマンドレットは、ユーザーが項目の内容を削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="0dcfa-118">(このサンプルで動的パラメーターを追加する方法が表示されない、`Clear-Content`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>

- <span data-ttu-id="0dcfa-119">上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドの動作を変更する、`Get-Content`コマンドレットは、ユーザーが項目のコンテンツを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="0dcfa-120">(このサンプルで動的パラメーターを追加する方法が表示されない、`Get-Content`コマンドレットです。)。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>

- <span data-ttu-id="0dcfa-121">上書き、 [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter)メソッドの動作を変更する、`Set-Content`コマンドレットは、ユーザーが項目のコンテンツを更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-121">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="0dcfa-122">(このサンプルで動的パラメーターを追加する方法が表示されない、`Set-Content`コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="0dcfa-123">例</span><span class="sxs-lookup"><span data-stu-id="0dcfa-123">Example</span></span>

<span data-ttu-id="0dcfa-124">このサンプルでは、clear、取得、および Microsoft Access データの基本項目の内容を設定するためのメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0dcfa-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="0dcfa-125">参照</span><span class="sxs-lookup"><span data-stu-id="0dcfa-125">See Also</span></span>

[<span data-ttu-id="0dcfa-126">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="0dcfa-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="0dcfa-127">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="0dcfa-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="0dcfa-128">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="0dcfa-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="0dcfa-129">Windows PowerShell プロバイダーのデザイン</span><span class="sxs-lookup"><span data-stu-id="0dcfa-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)