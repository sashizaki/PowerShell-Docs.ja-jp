---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample06
description: AccessDBProviderSample06
ms.openlocfilehash: a2037c6f13ba24ba2dcb4ffecbd802566452d64e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92656933"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="e95a3-103">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="e95a3-103">AccessDBProviderSample06</span></span>

<span data-ttu-id="e95a3-104">このサンプル `Clear-Content` では、、 `Get-Content` 、およびコマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示し `Set-Content` ます。</span><span class="sxs-lookup"><span data-stu-id="e95a3-104">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="e95a3-105">これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e95a3-105">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="e95a3-106">このサンプルのプロバイダークラスは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを実装しています。この[クラスは、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生していますが、</span><span class="sxs-lookup"><span data-stu-id="e95a3-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e95a3-107">対象</span><span class="sxs-lookup"><span data-stu-id="e95a3-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e95a3-108">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e95a3-108">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="e95a3-109">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="e95a3-109">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="e95a3-110">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e95a3-110">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="e95a3-111">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e95a3-111">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="e95a3-112">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e95a3-112">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="e95a3-113">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="e95a3-113">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="e95a3-114">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e95a3-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="e95a3-115">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e95a3-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="e95a3-116">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="e95a3-116">Declaring the `CmdletProvider` attribute.</span></span>
- <span data-ttu-id="e95a3-117">[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを宣言する、system.servicemodel クラスから派生したプロバイダークラスを定義します。[このクラスは](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)、このクラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="e95a3-117">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>
- <span data-ttu-id="e95a3-118">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを上書きして、コマンドレットの動作を変更し `Clear-Content` 、ユーザーが項目からコンテンツを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e95a3-118">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="e95a3-119">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Clear-Content` )。</span><span class="sxs-lookup"><span data-stu-id="e95a3-119">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>
- <span data-ttu-id="e95a3-120">[Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを上書きして、コマンドレットの動作を変更し `Get-Content` 、ユーザーが項目の内容を取得できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="e95a3-120">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="e95a3-121">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Get-Content` )。</span><span class="sxs-lookup"><span data-stu-id="e95a3-121">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>
- <span data-ttu-id="e95a3-122">コマンドレットの動作を変更して、ユーザーが項目の内容を更新できるようにするには、このメソッドを上書き[します。](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) `Set-Content`</span><span class="sxs-lookup"><span data-stu-id="e95a3-122">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="e95a3-123">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Set-Content` )。</span><span class="sxs-lookup"><span data-stu-id="e95a3-123">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="e95a3-124">例</span><span class="sxs-lookup"><span data-stu-id="e95a3-124">Example</span></span>

<span data-ttu-id="e95a3-125">このサンプルでは、Microsoft Access データベースの項目の内容をクリア、取得、および設定するために必要なメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e95a3-125">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="e95a3-126">参照</span><span class="sxs-lookup"><span data-stu-id="e95a3-126">See Also</span></span>

[<span data-ttu-id="e95a3-127">システムの................</span><span class="sxs-lookup"><span data-stu-id="e95a3-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="e95a3-128">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="e95a3-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="e95a3-129">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="e95a3-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="e95a3-130">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="e95a3-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
