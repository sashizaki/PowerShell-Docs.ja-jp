---
title: AccessDBProviderSample02 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf9351e-157f-4d48-8b8f-1fd64855b682
caps.latest.revision: 10
ms.openlocfilehash: 219f8c2367939d16da928ede789843669b4451c6
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633415"
---
# <a name="accessdbprovidersample02"></a><span data-ttu-id="c36e1-102">AccessDBProviderSample02</span><span class="sxs-lookup"><span data-stu-id="c36e1-102">AccessDBProviderSample02</span></span>

<span data-ttu-id="c36e1-103">このサンプルでは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) \* メソッドと[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きし `New-PSDrive` て、コマンドレットとコマンドレットの呼び出しをサポートする方法を示しています。この例を次に示し `Remove-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="c36e1-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods to support calls to the `New-PSDrive` and `Remove-PSDrive` cmdlets.</span></span> <span data-ttu-id="c36e1-104">このサンプルのプロバイダークラスは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="c36e1-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c36e1-105">対象</span><span class="sxs-lookup"><span data-stu-id="c36e1-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c36e1-106">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c36e1-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="c36e1-107">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="c36e1-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="c36e1-108">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36e1-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="c36e1-109">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c36e1-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="c36e1-110">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36e1-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="c36e1-111">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="c36e1-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="c36e1-112">「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36e1-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="c36e1-113">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36e1-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="c36e1-114">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c36e1-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="c36e1-115">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="c36e1-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="c36e1-116">[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスによって駆動されるプロバイダークラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c36e1-116">Defining a provider class that drives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span>

- <span data-ttu-id="c36e1-117">新しいドライブの作成をサポートするように[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c36e1-117">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to support creating new drives.</span></span> <span data-ttu-id="c36e1-118">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `New-PSDrive` )。</span><span class="sxs-lookup"><span data-stu-id="c36e1-118">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="c36e1-119">既存のドライブの削除をサポートするように[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c36e1-119">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

## <a name="example"></a><span data-ttu-id="c36e1-120">例</span><span class="sxs-lookup"><span data-stu-id="c36e1-120">Example</span></span>

<span data-ttu-id="c36e1-121">このサンプルでは、 [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドと[Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きする方法を示しています。この例では、このメソッドを上書きしています。</span><span class="sxs-lookup"><span data-stu-id="c36e1-121">This sample shows how to overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods.</span></span> <span data-ttu-id="c36e1-122">このサンプルプロバイダーでは、ドライブの作成時に、接続情報がオブジェクトに格納され `AccessDBPsDriveInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="c36e1-122">For this sample provider, when a drive is created its connection information is stored in an `AccessDBPsDriveInfo` object.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="c36e1-123">参照</span><span class="sxs-lookup"><span data-stu-id="c36e1-123">See Also</span></span>

[<span data-ttu-id="c36e1-124">システムの................</span><span class="sxs-lookup"><span data-stu-id="c36e1-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="c36e1-125">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="c36e1-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="c36e1-126">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="c36e1-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="c36e1-127">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="c36e1-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
