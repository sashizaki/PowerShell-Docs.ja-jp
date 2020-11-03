---
description: Windows Management Instrumentation (WMI) は、Common Information Model (CIM) を使用して、先進企業のシステム、アプリケーション、ネットワーク、デバイス、およびその他の管理可能なコンポーネントを表します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223208"
---
# <a name="about-wmi"></a><span data-ttu-id="b3c94-104">WMI について</span><span class="sxs-lookup"><span data-stu-id="b3c94-104">About WMI</span></span>

## <a name="short-description"></a><span data-ttu-id="b3c94-105">概要</span><span class="sxs-lookup"><span data-stu-id="b3c94-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b3c94-106">Windows Management Instrumentation (WMI) は、Common Information Model (CIM) を使用して、先進企業のシステム、アプリケーション、ネットワーク、デバイス、およびその他の管理可能なコンポーネントを表します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-106">Windows Management Instrumentation (WMI) uses the Common Information Model (CIM) to represent systems, applications, networks, devices, and other manageable components of the modern enterprise.</span></span>

## <a name="long-description"></a><span data-ttu-id="b3c94-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="b3c94-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b3c94-108">Windows Management Instrumentation (WMI) は、業界標準の Web-Based Enterprise Management (WBEM) を Microsoft が実装したものです。</span><span class="sxs-lookup"><span data-stu-id="b3c94-108">Windows Management Instrumentation (WMI) is Microsoft's implementation of Web-Based Enterprise Management (WBEM), the industry standard.</span></span>

<span data-ttu-id="b3c94-109">従来の WMI は、DCOM を使用してネットワークデバイスと通信し、リモートシステムを管理します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-109">Classic WMI uses DCOM to communicate with networked devices to manage remote systems.</span></span> <span data-ttu-id="b3c94-110">Windows PowerShell 3.0 では、WinRM を使用して DCOM の依存関係を削除する CIM プロバイダーモデルが導入されています。</span><span class="sxs-lookup"><span data-stu-id="b3c94-110">Windows PowerShell 3.0 introduces a CIM provider model that uses WinRM to remove the dependency on DCOM.</span></span> <span data-ttu-id="b3c94-111">また、この CIM プロバイダーモデルでは、開発者がネイティブコード (C) で Windows PowerShell コマンドレットを記述できるようにする新しい WMI プロバイダー Api も使用 \+ \+ します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-111">This CIM provider model also uses new WMI provider APIs that enable developers to write Windows PowerShell cmdlets in native code (C\+\+).</span></span>

<span data-ttu-id="b3c94-112">WMI プロバイダーと Windows PowerShell プロバイダーを混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b3c94-112">Do not confuse WMI providers with Windows PowerShell providers.</span></span> <span data-ttu-id="b3c94-113">多くの Windows 機能には、管理機能を公開する WMI プロバイダーが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b3c94-113">Many Windows features have an associated WMI provider that exposes their management capabilities.</span></span> <span data-ttu-id="b3c94-114">WMI プロバイダーを取得するには、次のクエリのように __Provider WMI クラスのインスタンスを取得する WMI クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-114">To get WMI providers, run a WMI query that gets instances of the __Provider WMI class, such as the following query.</span></span>

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a><span data-ttu-id="b3c94-115">WMI の3つのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="b3c94-115">THREE COMPONENTS OF WMI</span></span>

<span data-ttu-id="b3c94-116">WMI の次の3つのコンポーネントは、Windows PowerShell と対話します。名前空間、プロバイダー、およびクラスです。</span><span class="sxs-lookup"><span data-stu-id="b3c94-116">The following three components of WMI interact with Windows PowerShell: Namespaces, Providers, and Classes.</span></span>

<span data-ttu-id="b3c94-117">Wmi 名前空間は、WMI プロバイダーと WMI クラスを関連コンポーネントのグループに整理します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-117">WMI Namespaces organize WMI providers and WMI classes into groups of related components.</span></span> <span data-ttu-id="b3c94-118">このようにして、.NET Framework 名前空間に似ています。</span><span class="sxs-lookup"><span data-stu-id="b3c94-118">In this way, they are similar to .NET Framework namespaces.</span></span>
<span data-ttu-id="b3c94-119">名前空間は物理的な場所ではありませんが、論理データベースに似ています。</span><span class="sxs-lookup"><span data-stu-id="b3c94-119">Namespaces are not physical locations, but are more like logical databases.</span></span>
<span data-ttu-id="b3c94-120">すべての WMI 名前空間は、__Namespace システムクラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b3c94-120">All WMI namespaces are instances of the __Namespace system class.</span></span> <span data-ttu-id="b3c94-121">既定の WMI 名前空間は、ルート \/ CIMV2 (Microsoft Windows 2000 以降) です。</span><span class="sxs-lookup"><span data-stu-id="b3c94-121">The default WMI namespace is Root\/CIMV2 (since Microsoft Windows 2000).</span></span> <span data-ttu-id="b3c94-122">Windows PowerShell を使用して現在のセッションで WMI 名前空間を取得するには、次の形式のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-122">To use Windows PowerShell to get WMI namespaces in the current session, use a command with the following format.</span></span>

```powershell
Get-WmiObject -Class __Namespace
```

<span data-ttu-id="b3c94-123">他の名前空間の WMI 名前空間を取得するには、Namespace パラメーターを使用して検索の場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-123">To get WMI namespaces in other namespaces, use the Namespace parameter to change the location of the search.</span></span> <span data-ttu-id="b3c94-124">次のコマンドは、Root/Cimv2/Applications 名前空間に存在する WMI 名前空間を検索します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-124">The following command finds WMI namespaces that reside in the Root/Cimv2/Applications namespace.</span></span>

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

<span data-ttu-id="b3c94-125">WMI 名前空間は階層構造です。</span><span class="sxs-lookup"><span data-stu-id="b3c94-125">WMI namespaces are hierarchical.</span></span> <span data-ttu-id="b3c94-126">したがって、特定のシステム上のすべての名前空間の一覧を取得するには、ルート名前空間から開始する再帰クエリを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3c94-126">Therefore, obtaining a list of all namespaces on a particular system requires performing a recursive query starting at the root namespace.</span></span>

<span data-ttu-id="b3c94-127">WMI プロバイダーは、Windows の管理可能なオブジェクトに関する情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-127">WMI Providers expose information about Windows manageable objects.</span></span> <span data-ttu-id="b3c94-128">プロバイダーは、コンポーネントからデータを取得し、WMI を介して Windows PowerShell などの管理アプリケーションにそのデータを渡します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-128">A provider retrieves data from a component, and passes that data through WMI to a management application, such as Windows PowerShell.</span></span> <span data-ttu-id="b3c94-129">ほとんどの WMI プロバイダーは動的プロバイダーです。つまり、管理アプリケーションから要求されたときにデータを動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-129">Most WMI providers are dynamic providers, which means that they obtain the data dynamically when it is requested through the management application.</span></span>

## <a name="finding-wmi-classes"></a><span data-ttu-id="b3c94-130">検索 (WMI クラスを)</span><span class="sxs-lookup"><span data-stu-id="b3c94-130">FINDING WMI CLASSES</span></span>

<span data-ttu-id="b3c94-131">Windows 8 の既定のインストールでは、1100を超える WMI クラスがルート Cimv2 に存在 \/ します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-131">In a default installation of Windows 8, there are more than 1,100 WMI classes in Root\/Cimv2.</span></span> <span data-ttu-id="b3c94-132">この多くの WMI クラスを使用すると、特定のタスクを実行するために使用する適切な WMI クラスを特定することが困難になります。</span><span class="sxs-lookup"><span data-stu-id="b3c94-132">With this many WMI classes, the challenge becomes identifying the appropriate WMI class to use to perform a specific task.</span></span> <span data-ttu-id="b3c94-133">Windows PowerShell 3.0 には、特定のトピックに関連する WMI クラスを見つけるための2つの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b3c94-133">Windows PowerShell 3.0 provides two ways to find WMI classes that are related to a specific topic.</span></span>

<span data-ttu-id="b3c94-134">たとえば、 \\ ディスクに関連付けられているルート CIMV2 wmi 名前空間内の WMI クラスを検索するには、次に示すようなクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3c94-134">For example,to find WMI classes in the root\\CIMV2 WMI namespace that are related to disks, you can use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *disk*
```

<span data-ttu-id="b3c94-135">メモリに関連する WMI クラスを検索するには、次に示すようなクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b3c94-135">To find WMI classes that are related to memory, you might use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *memory*
```

<span data-ttu-id="b3c94-136">CIM コマンドレットには、WMI クラスを検出する機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="b3c94-136">The CIM cmdlets also provide the ability to discover WMI classes.</span></span> <span data-ttu-id="b3c94-137">これを行うには、Get-CIMClass コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-137">To do this, use the Get-CIMClass cmdlet.</span></span> <span data-ttu-id="b3c94-138">ここに示すコマンドは、ビデオに関連する WMI クラスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b3c94-138">The command shown here lists WMI classes related to video.</span></span>

```powershell
Get-CimClass *video*
```

<span data-ttu-id="b3c94-139">タブ拡張は、WMI 名前空間を変更するときに機能します。したがって、タブ拡張を使用すると、サブ WMI 名前空間を簡単に検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b3c94-139">Tab expansion works when changing WMI namespaces, and therefore use of tab expansion makes sub-WMI namespaces easily discoverable.</span></span> <span data-ttu-id="b3c94-140">次の例では、Get-CimClass コマンドレットを使用して、電源設定に関連する WMI クラスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-140">In the following example, the Get-CimClass cmdlet lists WMI classes related to power settings.</span></span>
<span data-ttu-id="b3c94-141">検索するには、名前空間を入力し、 `root/CIMV2/` tab キーを何度か押して、power 名前空間が表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="b3c94-141">To find it, type the `root/CIMV2/` namespace and then press the Tab key several times until the power namespace appears.</span></span> <span data-ttu-id="b3c94-142">次にコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="b3c94-142">Here is the command:</span></span>

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
