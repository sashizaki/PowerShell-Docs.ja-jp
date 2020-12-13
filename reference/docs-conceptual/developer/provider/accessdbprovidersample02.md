---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample02
description: AccessDBProviderSample02
ms.openlocfilehash: ebba2381370cf73f1e39015990f81dc4fd6dd937
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667438"
---
# <a name="accessdbprovidersample02"></a><span data-ttu-id="9200a-103">AccessDBProviderSample02</span><span class="sxs-lookup"><span data-stu-id="9200a-103">AccessDBProviderSample02</span></span>

<span data-ttu-id="9200a-104">このサンプルでは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) \* メソッドと [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) メソッドを上書きし `New-PSDrive` て、コマンドレットとコマンドレットの呼び出しをサポートする方法を示しています。この例を次に示し `Remove-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="9200a-104">This sample shows how to overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods to support calls to the `New-PSDrive` and `Remove-PSDrive` cmdlets.</span></span> <span data-ttu-id="9200a-105">このサンプルのプロバイダークラスは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="9200a-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="9200a-106">対象</span><span class="sxs-lookup"><span data-stu-id="9200a-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9200a-107">プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9200a-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="9200a-108">...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="9200a-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="9200a-109">「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9200a-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="9200a-110">[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9200a-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="9200a-111">「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9200a-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="9200a-112">...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="9200a-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="9200a-113">「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9200a-113">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="9200a-114">プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9200a-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="9200a-115">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9200a-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="9200a-116">属性を宣言 `CmdletProvider` しています。</span><span class="sxs-lookup"><span data-stu-id="9200a-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="9200a-117">[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスによって駆動されるプロバイダークラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="9200a-117">Defining a provider class that drives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span>

- <span data-ttu-id="9200a-118">新しいドライブの作成をサポートするように [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) メソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9200a-118">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to support creating new drives.</span></span> <span data-ttu-id="9200a-119">(このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `New-PSDrive` )。</span><span class="sxs-lookup"><span data-stu-id="9200a-119">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="9200a-120">既存のドライブの削除をサポートするように [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) メソッドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9200a-120">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

## <a name="example"></a><span data-ttu-id="9200a-121">例</span><span class="sxs-lookup"><span data-stu-id="9200a-121">Example</span></span>

<span data-ttu-id="9200a-122">このサンプルでは、 [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) メソッドと [Drivecmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) メソッドを上書きする方法を示しています。この例では、このメソッドを上書きしています。</span><span class="sxs-lookup"><span data-stu-id="9200a-122">This sample shows how to overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods.</span></span> <span data-ttu-id="9200a-123">このサンプルプロバイダーでは、ドライブの作成時に、接続情報がオブジェクトに格納され `AccessDBPsDriveInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="9200a-123">For this sample provider, when a drive is created its connection information is stored in an `AccessDBPsDriveInfo` object.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="9200a-124">参照</span><span class="sxs-lookup"><span data-stu-id="9200a-124">See Also</span></span>

[<span data-ttu-id="9200a-125">システムの................</span><span class="sxs-lookup"><span data-stu-id="9200a-125">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="9200a-126">Containercmdletprovider (システム管理)</span><span class="sxs-lookup"><span data-stu-id="9200a-126">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="9200a-127">システムの管理...。</span><span class="sxs-lookup"><span data-stu-id="9200a-127">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="9200a-128">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="9200a-128">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
